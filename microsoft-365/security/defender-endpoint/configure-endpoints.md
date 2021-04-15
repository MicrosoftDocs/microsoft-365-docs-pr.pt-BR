---
title: Ferramentas e métodos de integração para computadores Windows 10
description: Integração de dispositivos Windows 10 para que eles possam enviar dados do sensor para o sensor do Microsoft Defender ATP
keywords: Integração de dispositivos Windows 10, política de grupo, gerenciador de configuração de ponto de extremidade, gerenciamento de dispositivo móvel, script local, gp, sccm, mdm, intune
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 77b843f9526d8b100845403bc8d2df4bf3259471
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760207"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="9dbb1-104">Ferramentas e métodos de integração para computadores Windows 10</span><span class="sxs-lookup"><span data-stu-id="9dbb1-104">Onboarding tools and methods for Windows 10 devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9dbb1-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="9dbb1-105">**Applies to:**</span></span>
- [<span data-ttu-id="9dbb1-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="9dbb1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9dbb1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9dbb1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="9dbb1-108">Prevenção contra perda de dados do Microsoft 365 Endpoint (DLP)</span><span class="sxs-lookup"><span data-stu-id="9dbb1-108">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [<span data-ttu-id="9dbb1-109">Gerenciamento de riscos do Microsoft 365 Insider</span><span class="sxs-lookup"><span data-stu-id="9dbb1-109">Microsoft 365 Insider risk management</span></span>](/microsoft-365/compliance/insider-risk-management)

><span data-ttu-id="9dbb1-110">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="9dbb1-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9dbb1-111">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="9dbb1-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="9dbb1-112">Os dispositivos em sua organização devem ser configurados para que o serviço Defender for Endpoint possa obter dados do sensor deles.</span><span class="sxs-lookup"><span data-stu-id="9dbb1-112">Devices in your organization must be configured so that the Defender for Endpoint service can get sensor data from them.</span></span> <span data-ttu-id="9dbb1-113">Há vários métodos e ferramentas de implantação que você pode usar para configurar os dispositivos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="9dbb1-113">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="9dbb1-114">As seguintes ferramentas de implantação e métodos são suportados:</span><span class="sxs-lookup"><span data-stu-id="9dbb1-114">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="9dbb1-115">Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="9dbb1-115">Group Policy</span></span>
- <span data-ttu-id="9dbb1-116">Gerenciador de Configuração do Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="9dbb1-116">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="9dbb1-117">Gerenciamento de dispositivo móvel (incluindo o Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="9dbb1-117">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="9dbb1-118">Script local</span><span class="sxs-lookup"><span data-stu-id="9dbb1-118">Local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="9dbb1-119">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="9dbb1-119">In this section</span></span>
<span data-ttu-id="9dbb1-120">Tópico</span><span class="sxs-lookup"><span data-stu-id="9dbb1-120">Topic</span></span> | <span data-ttu-id="9dbb1-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="9dbb1-121">Description</span></span>
:---|:---
[<span data-ttu-id="9dbb1-122">Integração de dispositivos Windows 10 usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="9dbb1-122">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md) | <span data-ttu-id="9dbb1-123">Use a Política de Grupo para implantar o pacote de configuração em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9dbb1-123">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="9dbb1-124">Integração de dispositivos Windows usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9dbb1-124">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) | <span data-ttu-id="9dbb1-125">Você pode usar o Microsoft Endpoint Manager (branch atual) versão 1606 ou o Microsoft Endpoint Manager (branch atual) versão 1602 ou anterior para implantar o pacote de configuração em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9dbb1-125">You can use either use Microsoft Endpoint Manager (current branch) version 1606 or Microsoft Endpoint Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="9dbb1-126">Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel</span><span class="sxs-lookup"><span data-stu-id="9dbb1-126">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md) | <span data-ttu-id="9dbb1-127">Use as ferramentas de Gerenciamento de Dispositivo Móvel ou o Microsoft Intune para implantar o pacote de configuração no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9dbb1-127">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="9dbb1-128">Integrar dispositivos Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="9dbb1-128">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md) | <span data-ttu-id="9dbb1-129">Saiba como usar o script local para implantar o pacote de configuração nos pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="9dbb1-129">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="9dbb1-130">Dispositivos integrados de VDI (Virtual Desktop Infrastructure) não persistente</span><span class="sxs-lookup"><span data-stu-id="9dbb1-130">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md) | <span data-ttu-id="9dbb1-131">Saiba como usar o pacote de configuração para configurar dispositivos VDI.</span><span class="sxs-lookup"><span data-stu-id="9dbb1-131">Learn how to use the configuration package to configure VDI devices.</span></span>


><span data-ttu-id="9dbb1-132">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="9dbb1-132">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9dbb1-133">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="9dbb1-133">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
