---
title: Configurar o Microsoft Defender para Ponto de Extremidade para recursos do Android
description: Descreve como configurar o Microsoft Defender para Ponto de Extremidade no Android
keywords: microsoft, defender, Microsoft Defender for Endpoint, mde, android, configuration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 462fa6177ee35d5d988efa985422b499e2339ff4
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935312"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a><span data-ttu-id="3a38b-104">Configurar o Defender para Ponto de Extremidade em recursos do Android</span><span class="sxs-lookup"><span data-stu-id="3a38b-104">Configure Defender for Endpoint on Android features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3a38b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="3a38b-105">**Applies to:**</span></span>
- [<span data-ttu-id="3a38b-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="3a38b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3a38b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3a38b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a><span data-ttu-id="3a38b-108">Acesso condicional com o Defender para Ponto de Extremidade no Android</span><span class="sxs-lookup"><span data-stu-id="3a38b-108">Conditional Access with Defender for Endpoint on Android</span></span>  
<span data-ttu-id="3a38b-109">O Microsoft Defender para Ponto de Extremidade no Android juntamente com o Microsoft Intune e o Azure Active Directory permite a imposição de políticas de conformidade de dispositivo e acesso condicional com base nos níveis de risco do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3a38b-109">Microsoft Defender for Endpoint on Android along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="3a38b-110">O Defender for Endpoint é uma solução MTD (Mobile Threat Defense) que você pode implantar para aproveitar esse recurso por meio do Intune.</span><span class="sxs-lookup"><span data-stu-id="3a38b-110">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="3a38b-111">Para obter mais informações sobre como configurar o Defender para Ponto de Extremidade no Android e no Acesso Condicional, consulte [Defender for Endpoint e Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="3a38b-111">For more information about how to set up Defender for Endpoint on Android and Conditional Access, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="3a38b-112">Configurar indicadores personalizados</span><span class="sxs-lookup"><span data-stu-id="3a38b-112">Configure custom indicators</span></span>  

> [!NOTE]
> <span data-ttu-id="3a38b-113">O Defender para Ponto de Extremidade no Android só dá suporte à criação de indicadores personalizados para endereços IP e URLs/domínios.</span><span class="sxs-lookup"><span data-stu-id="3a38b-113">Defender for Endpoint on Android only supports creating custom indicators for IP addresses and URLs/domains.</span></span>

<span data-ttu-id="3a38b-114">O Defender para Ponto de Extremidade no Android permite que os administradores configurem indicadores personalizados para dar suporte a dispositivos Android também.</span><span class="sxs-lookup"><span data-stu-id="3a38b-114">Defender for Endpoint on Android enables admins to configure custom indicators to support Android devices as well.</span></span> <span data-ttu-id="3a38b-115">Para obter mais informações sobre como configurar indicadores personalizados, consulte [Manage indicators](manage-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="3a38b-115">For more information on how to configure custom indicators, see [Manage indicators](manage-indicators.md).</span></span>

## <a name="configure-web-protection"></a><span data-ttu-id="3a38b-116">Configurar a proteção da Web</span><span class="sxs-lookup"><span data-stu-id="3a38b-116">Configure web protection</span></span>
<span data-ttu-id="3a38b-117">O Defender para Ponto de Extremidade no Android permite aos administradores de IT a capacidade de configurar o recurso de proteção da Web.</span><span class="sxs-lookup"><span data-stu-id="3a38b-117">Defender for Endpoint on Android allows IT Administrators the ability to configure the web protection feature.</span></span> <span data-ttu-id="3a38b-118">Esse recurso está disponível no Centro de Administração do Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="3a38b-118">This capability is available within the Microsoft Endpoint Manager Admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="3a38b-119">O Defender para Ponto de Extremidade no Android usaria uma VPN para fornecer o recurso de Proteção da Web.</span><span class="sxs-lookup"><span data-stu-id="3a38b-119">Defender for Endpoint on Android would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="3a38b-120">Esta não é uma VPN regular e é uma VPN local/auto-loop que não faz o tráfego fora do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3a38b-120">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="3a38b-121">Para obter mais informações, consulte [Configure Web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).</span><span class="sxs-lookup"><span data-stu-id="3a38b-121">For more information, see [Configure web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3a38b-122">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="3a38b-122">Related topics</span></span>
- [<span data-ttu-id="3a38b-123">Visão geral do Microsoft Defender para Ponto de Extremidade para Android</span><span class="sxs-lookup"><span data-stu-id="3a38b-123">Overview of Microsoft Defender for Endpoint on Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="3a38b-124">Implantar o Microsoft Defender para Ponto de Extremidade para Android com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3a38b-124">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
