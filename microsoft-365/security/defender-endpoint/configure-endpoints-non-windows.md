---
title: Integração de dispositivos que não são windows ao serviço microsoft defender para ponto de extremidade
description: Configure dispositivos que não são windows para que eles possam enviar dados do sensor para o serviço Microsoft Defender para Ponto de Extremidade.
keywords: integração de dispositivos que não são windows, macos, linux, gerenciamento de dispositivos, configurar dispositivos Windows ATP, configurar o Microsoft Defender para dispositivos de ponto de extremidade
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
ms.openlocfilehash: c78779cd4a8a329864b6ac7e0debfc30ca0b3a56
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893584"
---
# <a name="onboard-non-windows-devices"></a><span data-ttu-id="d9f64-104">Dispositivos Windows não integrados</span><span class="sxs-lookup"><span data-stu-id="d9f64-104">Onboard non-Windows devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d9f64-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d9f64-105">**Applies to:**</span></span>
- [<span data-ttu-id="d9f64-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d9f64-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d9f64-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d9f64-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="d9f64-108">**Plataformas**</span><span class="sxs-lookup"><span data-stu-id="d9f64-108">**Platforms**</span></span>
- <span data-ttu-id="d9f64-109">macOS</span><span class="sxs-lookup"><span data-stu-id="d9f64-109">macOS</span></span>
- <span data-ttu-id="d9f64-110">Linux</span><span class="sxs-lookup"><span data-stu-id="d9f64-110">Linux</span></span>

><span data-ttu-id="d9f64-111">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="d9f64-111">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d9f64-112">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="d9f64-112">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

<span data-ttu-id="d9f64-113">O Defender for Endpoint fornece uma experiência centralizada de operações de segurança para o Windows, bem como para plataformas que não são do Windows.</span><span class="sxs-lookup"><span data-stu-id="d9f64-113">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="d9f64-114">Você poderá ver alertas de vários sistemas operacionais com suporte (SO) no Centro de Segurança do Microsoft Defender e proteger melhor a rede da sua organização.</span><span class="sxs-lookup"><span data-stu-id="d9f64-114">You'll be able to see alerts from various supported operating systems (OS) in Microsoft Defender Security Center and better protect your organization's network.</span></span> 

<span data-ttu-id="d9f64-115">Você precisará saber as versões exatas do Linux e macOS compatíveis com o Defender para o Ponto de Extremidade para que a integração funcione.</span><span class="sxs-lookup"><span data-stu-id="d9f64-115">You'll need to know the exact Linux distros and macOS versions that are compatible with Defender for Endpoint for the integration to work.</span></span> <span data-ttu-id="d9f64-116">Para saber mais, confira:</span><span class="sxs-lookup"><span data-stu-id="d9f64-116">For more information, see:</span></span>
- [<span data-ttu-id="d9f64-117">Microsoft Defender para Ponto de Extremidade em requisitos do sistema Linux</span><span class="sxs-lookup"><span data-stu-id="d9f64-117">Microsoft Defender for Endpoint on Linux system requirements</span></span>](microsoft-defender-endpoint-linux.md#system-requirements)  
- <span data-ttu-id="d9f64-118">[Microsoft Defender para Ponto de Extremidade em requisitos do sistema macOS.](microsoft-defender-endpoint-mac.md#system-requirements)</span><span class="sxs-lookup"><span data-stu-id="d9f64-118">[Microsoft Defender for Endpoint on macOS system requirements](microsoft-defender-endpoint-mac.md#system-requirements).</span></span>

## <a name="onboarding-non-windows-devices"></a><span data-ttu-id="d9f64-119">Integrando dispositivos que não são windows</span><span class="sxs-lookup"><span data-stu-id="d9f64-119">Onboarding non-Windows devices</span></span>
<span data-ttu-id="d9f64-120">Você precisará seguir as etapas a seguir para a integração de dispositivos que não são windows:</span><span class="sxs-lookup"><span data-stu-id="d9f64-120">You'll need to take the following steps to onboard non-Windows devices:</span></span>
1. <span data-ttu-id="d9f64-121">Selecione seu método preferencial de integração:</span><span class="sxs-lookup"><span data-stu-id="d9f64-121">Select your preferred method of onboarding:</span></span>

   - <span data-ttu-id="d9f64-122">Para dispositivos macOS, você pode optar por integração por meio do Microsoft Defender para Ponto de Extremidade ou por meio de uma solução de terceiros.</span><span class="sxs-lookup"><span data-stu-id="d9f64-122">For macOS devices, you can choose to onboard through Microsoft Defender for Endpoint or through a third-party solution.</span></span> <span data-ttu-id="d9f64-123">Para obter mais informações, consulte [Microsoft Defender for Endpoint for Mac](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac).</span><span class="sxs-lookup"><span data-stu-id="d9f64-123">For more information, see [Microsoft Defender for Endpoint for Mac](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac).</span></span>

   - <span data-ttu-id="d9f64-124">Para outros dispositivos que não são do Windows, escolha **Integrar dispositivos que não são do Windows por meio da integração de terceiros.**</span><span class="sxs-lookup"><span data-stu-id="d9f64-124">For other non-Windows devices choose **Onboard non-Windows devices through third-party integration**.</span></span>   
    1. <span data-ttu-id="d9f64-125">No painel de navegação, selecione **Parceiros de**  >  **Interoperabilidade**.</span><span class="sxs-lookup"><span data-stu-id="d9f64-125">In the navigation pane, select **Interoperability** > **Partners**.</span></span> <span data-ttu-id="d9f64-126">Certifique-se de que a solução de terceiros está listada.</span><span class="sxs-lookup"><span data-stu-id="d9f64-126">Make sure the third-party solution is listed.</span></span>
    2. <span data-ttu-id="d9f64-127">Na guia **Aplicativos Parceiros,** selecione o parceiro que oferece suporte a seus dispositivos que não são windows.</span><span class="sxs-lookup"><span data-stu-id="d9f64-127">In the **Partner Applications** tab, select the partner that supports your non-Windows devices.</span></span>
    3. <span data-ttu-id="d9f64-128">Selecione **Abrir página do parceiro** para abrir a página do parceiro.</span><span class="sxs-lookup"><span data-stu-id="d9f64-128">Select **Open partner page** to open the partner's page.</span></span> <span data-ttu-id="d9f64-129">Siga as instruções fornecidas na página.</span><span class="sxs-lookup"><span data-stu-id="d9f64-129">Follow the instructions provided on the page.</span></span>
    4. <span data-ttu-id="d9f64-130">Depois de criar uma conta ou assinar a solução de parceiro, você deve chegar a um estágio em que um administrador global de locatários em sua organização é solicitado a aceitar uma solicitação de permissão do aplicativo parceiro.</span><span class="sxs-lookup"><span data-stu-id="d9f64-130">After creating an account or subscribing to the partner solution, you should get to a stage where a tenant Global Admin in your organization is asked to accept a permission request from the partner application.</span></span> <span data-ttu-id="d9f64-131">Leia a solicitação de permissão cuidadosamente para garantir que ela esteja alinhada com o serviço necessário.</span><span class="sxs-lookup"><span data-stu-id="d9f64-131">Read the permission request carefully to make sure that it is aligned with the service that you require.</span></span> 

        
2. <span data-ttu-id="d9f64-132">Execute um teste de detecção seguindo as instruções da solução de terceiros.</span><span class="sxs-lookup"><span data-stu-id="d9f64-132">Run a detection test by following the instructions of the third-party solution.</span></span>

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="d9f64-133">Offboard de dispositivos que não são windows</span><span class="sxs-lookup"><span data-stu-id="d9f64-133">Offboard non-Windows devices</span></span>

1. <span data-ttu-id="d9f64-134">Siga a documentação de terceiros para desconectar a solução de terceiros do Microsoft Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="d9f64-134">Follow the third-party's documentation to disconnect the third-party solution from Microsoft Defender for Endpoint.</span></span>

2. <span data-ttu-id="d9f64-135">Remova permissões para a solução de terceiros no locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d9f64-135">Remove permissions for the third-party solution in your Azure AD tenant.</span></span>
   1. <span data-ttu-id="d9f64-136">Entre no [portal do Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="d9f64-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
   2. <span data-ttu-id="d9f64-137">Selecione Aplicativos Corporativos **do Azure Active Directory >**.</span><span class="sxs-lookup"><span data-stu-id="d9f64-137">Select **Azure Active Directory > Enterprise Applications**.</span></span>
   3. <span data-ttu-id="d9f64-138">Selecione o aplicativo que você gostaria de fazer offboard.</span><span class="sxs-lookup"><span data-stu-id="d9f64-138">Select the application you'd like to offboard.</span></span>
   4. <span data-ttu-id="d9f64-139">Selecione o **botão Excluir.**</span><span class="sxs-lookup"><span data-stu-id="d9f64-139">Select the **Delete** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="d9f64-140">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d9f64-140">Related topics</span></span>
- [<span data-ttu-id="d9f64-141">Dispositivos integrados do Windows 10</span><span class="sxs-lookup"><span data-stu-id="d9f64-141">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="d9f64-142">Servidores de integração</span><span class="sxs-lookup"><span data-stu-id="d9f64-142">Onboard servers</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="d9f64-143">Definir as configurações de proxy e conectividade com a Internet</span><span class="sxs-lookup"><span data-stu-id="d9f64-143">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="d9f64-144">Solução de problemas de integração do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d9f64-144">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
