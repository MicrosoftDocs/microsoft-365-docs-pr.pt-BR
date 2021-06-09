---
title: Integração de dispositivos que não Windows para o serviço do Microsoft Defender para Ponto de Extremidade
description: Configure dispositivos não Windows para que eles possam enviar dados do sensor para o serviço Microsoft Defender para Ponto de Extremidade.
keywords: integração de dispositivos Windows, macos, linux, gerenciamento de dispositivos, configurar o Microsoft Defender para dispositivos de ponto de extremidade
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
ms.openlocfilehash: 265a7e9093638caa2111c7d1d82e51c8c2437d12
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845451"
---
# <a name="onboard-non-windows-devices"></a><span data-ttu-id="683c4-104">Dispositivos Windows não integrados</span><span class="sxs-lookup"><span data-stu-id="683c4-104">Onboard non-Windows devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="683c4-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="683c4-105">**Applies to:**</span></span>
- [<span data-ttu-id="683c4-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="683c4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="683c4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="683c4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="683c4-108">**Plataformas**</span><span class="sxs-lookup"><span data-stu-id="683c4-108">**Platforms**</span></span>
- <span data-ttu-id="683c4-109">macOS</span><span class="sxs-lookup"><span data-stu-id="683c4-109">macOS</span></span>
- <span data-ttu-id="683c4-110">Linux</span><span class="sxs-lookup"><span data-stu-id="683c4-110">Linux</span></span>

><span data-ttu-id="683c4-111">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="683c4-111">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="683c4-112">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="683c4-112">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

<span data-ttu-id="683c4-113">O Defender for Endpoint fornece uma experiência centralizada de operações de segurança para Windows, bem como plataformas que não Windows.</span><span class="sxs-lookup"><span data-stu-id="683c4-113">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="683c4-114">Você poderá ver alertas de vários sistemas operacionais com suporte (SO) no Central de Segurança do Microsoft Defender e proteger melhor a rede da sua organização.</span><span class="sxs-lookup"><span data-stu-id="683c4-114">You'll be able to see alerts from various supported operating systems (OS) in Microsoft Defender Security Center and better protect your organization's network.</span></span> 

<span data-ttu-id="683c4-115">Você precisará saber as versões exatas do Linux e macOS compatíveis com o Defender para o Ponto de Extremidade para que a integração funcione.</span><span class="sxs-lookup"><span data-stu-id="683c4-115">You'll need to know the exact Linux distros and macOS versions that are compatible with Defender for Endpoint for the integration to work.</span></span> <span data-ttu-id="683c4-116">Para saber mais, confira:</span><span class="sxs-lookup"><span data-stu-id="683c4-116">For more information, see:</span></span>
- [<span data-ttu-id="683c4-117">Microsoft Defender para Ponto de Extremidade em requisitos do sistema Linux</span><span class="sxs-lookup"><span data-stu-id="683c4-117">Microsoft Defender for Endpoint on Linux system requirements</span></span>](microsoft-defender-endpoint-linux.md#system-requirements)  
- <span data-ttu-id="683c4-118">[Microsoft Defender para Ponto de Extremidade em requisitos do sistema macOS.](microsoft-defender-endpoint-mac.md#system-requirements)</span><span class="sxs-lookup"><span data-stu-id="683c4-118">[Microsoft Defender for Endpoint on macOS system requirements](microsoft-defender-endpoint-mac.md#system-requirements).</span></span>

## <a name="onboarding-non-windows-devices"></a><span data-ttu-id="683c4-119">Integrando dispositivos que não Windows de segurança</span><span class="sxs-lookup"><span data-stu-id="683c4-119">Onboarding non-Windows devices</span></span>
<span data-ttu-id="683c4-120">Você precisará seguir as seguintes etapas para a integração de dispositivos que não Windows:</span><span class="sxs-lookup"><span data-stu-id="683c4-120">You'll need to take the following steps to onboard non-Windows devices:</span></span>
1. <span data-ttu-id="683c4-121">Selecione seu método preferencial de integração:</span><span class="sxs-lookup"><span data-stu-id="683c4-121">Select your preferred method of onboarding:</span></span>

   - <span data-ttu-id="683c4-122">Para dispositivos macOS, você pode optar por integração por meio do Microsoft Defender para Ponto de Extremidade ou por meio de uma solução de terceiros.</span><span class="sxs-lookup"><span data-stu-id="683c4-122">For macOS devices, you can choose to onboard through Microsoft Defender for Endpoint or through a third-party solution.</span></span> <span data-ttu-id="683c4-123">Para obter mais informações, consulte [Microsoft Defender for Endpoint on Mac](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac).</span><span class="sxs-lookup"><span data-stu-id="683c4-123">For more information, see [Microsoft Defender for Endpoint on Mac](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac).</span></span>

   - <span data-ttu-id="683c4-124">Para outros dispositivos que não Windows escolha Integrar dispositivos que não Windows por meio da **integração de terceiros.**</span><span class="sxs-lookup"><span data-stu-id="683c4-124">For other non-Windows devices choose **Onboard non-Windows devices through third-party integration**.</span></span>   
    1. <span data-ttu-id="683c4-125">No painel de navegação, selecione **Parceiros de**  >  **Interoperabilidade**.</span><span class="sxs-lookup"><span data-stu-id="683c4-125">In the navigation pane, select **Interoperability** > **Partners**.</span></span> <span data-ttu-id="683c4-126">Certifique-se de que a solução de terceiros está listada.</span><span class="sxs-lookup"><span data-stu-id="683c4-126">Make sure the third-party solution is listed.</span></span>
    2. <span data-ttu-id="683c4-127">Na guia **Aplicativos parceiros,** selecione o parceiro que oferece suporte aos dispositivos que não Windows.</span><span class="sxs-lookup"><span data-stu-id="683c4-127">In the **Partner Applications** tab, select the partner that supports your non-Windows devices.</span></span>
    3. <span data-ttu-id="683c4-128">Selecione **Abrir página do parceiro** para abrir a página do parceiro.</span><span class="sxs-lookup"><span data-stu-id="683c4-128">Select **Open partner page** to open the partner's page.</span></span> <span data-ttu-id="683c4-129">Siga as instruções fornecidas na página.</span><span class="sxs-lookup"><span data-stu-id="683c4-129">Follow the instructions provided on the page.</span></span>
    4. <span data-ttu-id="683c4-130">Depois de criar uma conta ou assinar a solução de parceiro, você deve chegar a um estágio em que um administrador global de locatários em sua organização é solicitado a aceitar uma solicitação de permissão do aplicativo parceiro.</span><span class="sxs-lookup"><span data-stu-id="683c4-130">After creating an account or subscribing to the partner solution, you should get to a stage where a tenant Global Admin in your organization is asked to accept a permission request from the partner application.</span></span> <span data-ttu-id="683c4-131">Leia a solicitação de permissão cuidadosamente para garantir que ela esteja alinhada com o serviço necessário.</span><span class="sxs-lookup"><span data-stu-id="683c4-131">Read the permission request carefully to make sure that it is aligned with the service that you require.</span></span> 

        
2. <span data-ttu-id="683c4-132">Execute um teste de detecção seguindo as instruções da solução de terceiros.</span><span class="sxs-lookup"><span data-stu-id="683c4-132">Run a detection test by following the instructions of the third-party solution.</span></span>

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="683c4-133">Dispositivos que não Windows offboard</span><span class="sxs-lookup"><span data-stu-id="683c4-133">Offboard non-Windows devices</span></span>

1. <span data-ttu-id="683c4-134">Siga a documentação de terceiros para desconectar a solução de terceiros do Microsoft Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="683c4-134">Follow the third-party's documentation to disconnect the third-party solution from Microsoft Defender for Endpoint.</span></span>

2. <span data-ttu-id="683c4-135">Remova permissões para a solução de terceiros no locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="683c4-135">Remove permissions for the third-party solution in your Azure AD tenant.</span></span>
   1. <span data-ttu-id="683c4-136">Entre no [portal do Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="683c4-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
   2. <span data-ttu-id="683c4-137">Selecione **Azure Active Directory > Enterprise Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="683c4-137">Select **Azure Active Directory > Enterprise Applications**.</span></span>
   3. <span data-ttu-id="683c4-138">Selecione o aplicativo que você gostaria de fazer offboard.</span><span class="sxs-lookup"><span data-stu-id="683c4-138">Select the application you'd like to offboard.</span></span>
   4. <span data-ttu-id="683c4-139">Selecione o **botão Excluir.**</span><span class="sxs-lookup"><span data-stu-id="683c4-139">Select the **Delete** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="683c4-140">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="683c4-140">Related topics</span></span>
- [<span data-ttu-id="683c4-141">Dispositivos integrados do Windows 10</span><span class="sxs-lookup"><span data-stu-id="683c4-141">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="683c4-142">Servidores de integração</span><span class="sxs-lookup"><span data-stu-id="683c4-142">Onboard servers</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="683c4-143">Definir as configurações de proxy e conectividade com a Internet</span><span class="sxs-lookup"><span data-stu-id="683c4-143">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="683c4-144">Solução de problemas de integração do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="683c4-144">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
