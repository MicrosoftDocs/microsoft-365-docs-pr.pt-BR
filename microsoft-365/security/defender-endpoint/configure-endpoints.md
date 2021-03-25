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
ms.openlocfilehash: 1831d8927e761827f9bbcee84551433b68e3c6cc
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165532"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="0e925-104">Ferramentas e métodos de integração para computadores Windows 10</span><span class="sxs-lookup"><span data-stu-id="0e925-104">Onboarding tools and methods for Windows 10 devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0e925-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="0e925-105">**Applies to:**</span></span>
- [<span data-ttu-id="0e925-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="0e925-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0e925-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0e925-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="0e925-108">Prevenção contra perda de dados do Microsoft 365 Endpoint (DLP)</span><span class="sxs-lookup"><span data-stu-id="0e925-108">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

><span data-ttu-id="0e925-109">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="0e925-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0e925-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="0e925-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="0e925-111">Os dispositivos em sua organização devem ser configurados para que o serviço Defender for Endpoint possa obter dados do sensor deles.</span><span class="sxs-lookup"><span data-stu-id="0e925-111">Devices in your organization must be configured so that the Defender for Endpoint service can get sensor data from them.</span></span> <span data-ttu-id="0e925-112">Há vários métodos e ferramentas de implantação que você pode usar para configurar os dispositivos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="0e925-112">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="0e925-113">As seguintes ferramentas de implantação e métodos são suportados:</span><span class="sxs-lookup"><span data-stu-id="0e925-113">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="0e925-114">Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="0e925-114">Group Policy</span></span>
- <span data-ttu-id="0e925-115">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0e925-115">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="0e925-116">Gerenciamento de dispositivo móvel (incluindo o Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="0e925-116">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="0e925-117">Script local</span><span class="sxs-lookup"><span data-stu-id="0e925-117">Local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="0e925-118">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="0e925-118">In this section</span></span>
<span data-ttu-id="0e925-119">Tópico</span><span class="sxs-lookup"><span data-stu-id="0e925-119">Topic</span></span> | <span data-ttu-id="0e925-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="0e925-120">Description</span></span>
:---|:---
[<span data-ttu-id="0e925-121">Integração de dispositivos Windows 10 usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="0e925-121">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md) | <span data-ttu-id="0e925-122">Use a Política de Grupo para implantar o pacote de configuração em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0e925-122">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="0e925-123">Integração de dispositivos Windows usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0e925-123">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) | <span data-ttu-id="0e925-124">Você pode usar o Microsoft Endpoint Manager (branch atual) versão 1606 ou o Microsoft Endpoint Manager (branch atual) versão 1602 ou anterior para implantar o pacote de configuração em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0e925-124">You can use either use Microsoft Endpoint Manager (current branch) version 1606 or Microsoft Endpoint Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="0e925-125">Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel</span><span class="sxs-lookup"><span data-stu-id="0e925-125">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md) | <span data-ttu-id="0e925-126">Use as ferramentas de Gerenciamento de Dispositivo Móvel ou o Microsoft Intune para implantar o pacote de configuração no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0e925-126">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="0e925-127">Integrar dispositivos Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="0e925-127">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md) | <span data-ttu-id="0e925-128">Saiba como usar o script local para implantar o pacote de configuração nos pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="0e925-128">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="0e925-129">Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)</span><span class="sxs-lookup"><span data-stu-id="0e925-129">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md) | <span data-ttu-id="0e925-130">Saiba como usar o pacote de configuração para configurar dispositivos VDI.</span><span class="sxs-lookup"><span data-stu-id="0e925-130">Learn how to use the configuration package to configure VDI devices.</span></span>


><span data-ttu-id="0e925-131">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="0e925-131">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0e925-132">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="0e925-132">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
