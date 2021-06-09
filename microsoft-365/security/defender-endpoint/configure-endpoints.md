---
title: Ferramentas e métodos de integração para computadores Windows 10
description: Integração Windows 10 dispositivos para que eles possam enviar dados do sensor para o sensor do Microsoft Defender para Ponto de Extremidade
keywords: Integração Windows 10, política de grupo, gerenciador de configuração de ponto de extremidade, gerenciamento de dispositivo móvel, script local, gp, sccm, mdm, intune
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
ms.openlocfilehash: f1ef2670a1ca749e0a2f1ebc96300d4eca043bf8
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51892821"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="c74d8-104">Ferramentas e métodos de integração para computadores Windows 10</span><span class="sxs-lookup"><span data-stu-id="c74d8-104">Onboarding tools and methods for Windows 10 devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c74d8-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c74d8-105">**Applies to:**</span></span>
- [<span data-ttu-id="c74d8-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c74d8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c74d8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c74d8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="c74d8-108">Microsoft 365 Prevenção contra perda de dados do ponto de extremidade (DLP)</span><span class="sxs-lookup"><span data-stu-id="c74d8-108">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [<span data-ttu-id="c74d8-109">Microsoft 365 Gerenciamento de riscos insider</span><span class="sxs-lookup"><span data-stu-id="c74d8-109">Microsoft 365 Insider risk management</span></span>](/microsoft-365/compliance/insider-risk-management)

><span data-ttu-id="c74d8-110">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="c74d8-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c74d8-111">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="c74d8-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="c74d8-112">Os dispositivos em sua organização devem ser configurados para que o serviço Defender for Endpoint possa obter dados do sensor deles.</span><span class="sxs-lookup"><span data-stu-id="c74d8-112">Devices in your organization must be configured so that the Defender for Endpoint service can get sensor data from them.</span></span> <span data-ttu-id="c74d8-113">Há vários métodos e ferramentas de implantação que você pode usar para configurar os dispositivos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c74d8-113">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="c74d8-114">As seguintes ferramentas de implantação e métodos são suportados:</span><span class="sxs-lookup"><span data-stu-id="c74d8-114">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="c74d8-115">Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="c74d8-115">Group Policy</span></span>
- <span data-ttu-id="c74d8-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c74d8-116">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="c74d8-117">Gerenciamento de dispositivo móvel (incluindo Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="c74d8-117">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="c74d8-118">Script local</span><span class="sxs-lookup"><span data-stu-id="c74d8-118">Local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c74d8-119">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="c74d8-119">In this section</span></span>
<span data-ttu-id="c74d8-120">Tópico</span><span class="sxs-lookup"><span data-stu-id="c74d8-120">Topic</span></span> | <span data-ttu-id="c74d8-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="c74d8-121">Description</span></span>
:---|:---
[<span data-ttu-id="c74d8-122">Integração Windows 10 usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="c74d8-122">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md) | <span data-ttu-id="c74d8-123">Use a Política de Grupo para implantar o pacote de configuração em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c74d8-123">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="c74d8-124">Integração Windows dispositivos usando Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c74d8-124">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) | <span data-ttu-id="c74d8-125">Você pode usar o Microsoft Endpoint Manager versão 1606 ou Microsoft Endpoint Manager versão 1602 (filial atual) ou anterior para implantar o pacote de configuração em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c74d8-125">You can use either use Microsoft Endpoint Manager (current branch) version 1606 or Microsoft Endpoint Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="c74d8-126">Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel</span><span class="sxs-lookup"><span data-stu-id="c74d8-126">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md) | <span data-ttu-id="c74d8-127">Use ferramentas de Gerenciamento de Dispositivo Móvel ou Microsoft Intune para implantar o pacote de configuração no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c74d8-127">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="c74d8-128">Integrar dispositivos Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="c74d8-128">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md) | <span data-ttu-id="c74d8-129">Saiba como usar o script local para implantar o pacote de configuração nos pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="c74d8-129">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="c74d8-130">Dispositivos integrados de VDI (Virtual Desktop Infrastructure) não persistente</span><span class="sxs-lookup"><span data-stu-id="c74d8-130">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md) | <span data-ttu-id="c74d8-131">Saiba como usar o pacote de configuração para configurar dispositivos VDI.</span><span class="sxs-lookup"><span data-stu-id="c74d8-131">Learn how to use the configuration package to configure VDI devices.</span></span>


><span data-ttu-id="c74d8-132">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="c74d8-132">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c74d8-133">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="c74d8-133">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
