---
title: Integração de dispositivos que não são windows ao serviço microsoft defender para ponto de extremidade
description: Configure dispositivos que não são do Windows para que eles possam enviar dados do sensor para o serviço microsoft Defender ATP.
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
ms.openlocfilehash: c292c57c179a832728b03a7fc94fb7085d3ea0ec
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166072"
---
# <a name="onboard-non-windows-devices"></a><span data-ttu-id="cb390-104">Integração de dispositivos que não são windows</span><span class="sxs-lookup"><span data-stu-id="cb390-104">Onboard non-Windows devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cb390-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="cb390-105">**Applies to:**</span></span>
- [<span data-ttu-id="cb390-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="cb390-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cb390-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cb390-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="cb390-108">**Plataformas**</span><span class="sxs-lookup"><span data-stu-id="cb390-108">**Platforms**</span></span>
- <span data-ttu-id="cb390-109">macOS</span><span class="sxs-lookup"><span data-stu-id="cb390-109">macOS</span></span>
- <span data-ttu-id="cb390-110">Linux</span><span class="sxs-lookup"><span data-stu-id="cb390-110">Linux</span></span>

><span data-ttu-id="cb390-111">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="cb390-111">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cb390-112">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="cb390-112">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

<span data-ttu-id="cb390-113">O Defender for Endpoint fornece uma experiência centralizada de operações de segurança para o Windows, bem como para plataformas que não são do Windows.</span><span class="sxs-lookup"><span data-stu-id="cb390-113">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="cb390-114">Você poderá ver alertas de vários sistemas operacionais com suporte (SO) no Centro de Segurança do Microsoft Defender e proteger melhor a rede da sua organização.</span><span class="sxs-lookup"><span data-stu-id="cb390-114">You'll be able to see alerts from various supported operating systems (OS) in Microsoft Defender Security Center and better protect your organization's network.</span></span> 

<span data-ttu-id="cb390-115">Você precisará saber as versões exatas do Linux e macOS compatíveis com o Defender para o Ponto de Extremidade para que a integração funcione.</span><span class="sxs-lookup"><span data-stu-id="cb390-115">You'll need to know the exact Linux distros and macOS versions that are compatible with Defender for Endpoint for the integration to work.</span></span> <span data-ttu-id="cb390-116">Para mais informações, confira:</span><span class="sxs-lookup"><span data-stu-id="cb390-116">For more information, see:</span></span>
- [<span data-ttu-id="cb390-117">Microsoft Defender for Endpoint for Linux system requirements</span><span class="sxs-lookup"><span data-stu-id="cb390-117">Microsoft Defender for Endpoint for Linux system requirements</span></span>](microsoft-defender-endpoint-linux.md#system-requirements)  
- <span data-ttu-id="cb390-118">[Microsoft Defender for Endpoint for Mac system requirements](microsoft-defender-endpoint-mac.md#system-requirements).</span><span class="sxs-lookup"><span data-stu-id="cb390-118">[Microsoft Defender for Endpoint for Mac system requirements](microsoft-defender-endpoint-mac.md#system-requirements).</span></span>

## <a name="onboarding-non-windows-devices"></a><span data-ttu-id="cb390-119">Integrando dispositivos que não são windows</span><span class="sxs-lookup"><span data-stu-id="cb390-119">Onboarding non-Windows devices</span></span>
<span data-ttu-id="cb390-120">Você precisará seguir as etapas a seguir para a integração de dispositivos que não são windows:</span><span class="sxs-lookup"><span data-stu-id="cb390-120">You'll need to take the following steps to onboard non-Windows devices:</span></span>
1. <span data-ttu-id="cb390-121">Selecione seu método preferencial de integração:</span><span class="sxs-lookup"><span data-stu-id="cb390-121">Select your preferred method of onboarding:</span></span>

   - <span data-ttu-id="cb390-122">Para dispositivos macOS, você pode optar por integração por meio do Microsoft Defender ATP ou por meio de uma solução de terceiros.</span><span class="sxs-lookup"><span data-stu-id="cb390-122">For macOS devices, you can choose to onboard through Microsoft Defender ATP or through a third-party solution.</span></span> <span data-ttu-id="cb390-123">Para obter mais informações, consulte [Microsoft Defender for Endpoint for Mac](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac).</span><span class="sxs-lookup"><span data-stu-id="cb390-123">For more information, see [Microsoft Defender for Endpoint for Mac](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac).</span></span>
   - <span data-ttu-id="cb390-124">Para outros dispositivos que não são do Windows, escolha **Integrar dispositivos que não são do Windows por meio da integração de terceiros.**</span><span class="sxs-lookup"><span data-stu-id="cb390-124">For other non-Windows devices choose **Onboard non-Windows devices through third-party integration**.</span></span>   
       
     1. <span data-ttu-id="cb390-125">No painel de navegação, selecione **Parceiros de**  >  **Interoperabilidade**.</span><span class="sxs-lookup"><span data-stu-id="cb390-125">In the navigation pane, select **Interoperability** > **Partners**.</span></span> <span data-ttu-id="cb390-126">Certifique-se de que a solução de terceiros está listada.</span><span class="sxs-lookup"><span data-stu-id="cb390-126">Make sure the third-party solution is listed.</span></span>

        2. <span data-ttu-id="cb390-127">Na guia **Aplicativos Parceiros,** selecione o parceiro que oferece suporte a seus dispositivos que não são windows.</span><span class="sxs-lookup"><span data-stu-id="cb390-127">In the **Partner Applications** tab, select the partner that supports your non-Windows devices.</span></span>

        3. <span data-ttu-id="cb390-128">Selecione **Abrir página do parceiro** para abrir a página do parceiro.</span><span class="sxs-lookup"><span data-stu-id="cb390-128">Select **Open partner page** to open the partner's page.</span></span> <span data-ttu-id="cb390-129">Siga as instruções fornecidas na página.</span><span class="sxs-lookup"><span data-stu-id="cb390-129">Follow the instructions provided on the page.</span></span>

        4. <span data-ttu-id="cb390-130">Depois de criar uma conta ou assinar a solução de parceiro, você deve chegar a um estágio em que um administrador global de locatários em sua organização é solicitado a aceitar uma solicitação de permissão do aplicativo parceiro.</span><span class="sxs-lookup"><span data-stu-id="cb390-130">After creating an account or subscribing to the partner solution, you should get to a stage where a tenant Global Admin in your organization is asked to accept a permission request from the partner application.</span></span> <span data-ttu-id="cb390-131">Leia a solicitação de permissão cuidadosamente para garantir que ela esteja alinhada com o serviço necessário.</span><span class="sxs-lookup"><span data-stu-id="cb390-131">Read the permission request carefully to make sure that it is aligned with the service that you require.</span></span> 

        
2. <span data-ttu-id="cb390-132">Execute um teste de detecção seguindo as instruções da solução de terceiros.</span><span class="sxs-lookup"><span data-stu-id="cb390-132">Run a detection test by following the instructions of the third-party solution.</span></span>

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="cb390-133">Offboard de dispositivos que não são windows</span><span class="sxs-lookup"><span data-stu-id="cb390-133">Offboard non-Windows devices</span></span>

1. <span data-ttu-id="cb390-134">Siga a documentação de terceiros para desconectar a solução de terceiros do Microsoft Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="cb390-134">Follow the third-party's documentation to disconnect the third-party solution from Microsoft Defender for Endpoint.</span></span>

2. <span data-ttu-id="cb390-135">Remova permissões para a solução de terceiros no locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cb390-135">Remove permissions for the third-party solution in your Azure AD tenant.</span></span>
   1. <span data-ttu-id="cb390-136">Entre no [portal do Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="cb390-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
   2. <span data-ttu-id="cb390-137">Selecione Aplicativos Corporativos **do Azure Active Directory >**.</span><span class="sxs-lookup"><span data-stu-id="cb390-137">Select **Azure Active Directory > Enterprise Applications**.</span></span>
   3. <span data-ttu-id="cb390-138">Selecione o aplicativo que você gostaria de fazer offboard.</span><span class="sxs-lookup"><span data-stu-id="cb390-138">Select the application you'd like to offboard.</span></span>
   4. <span data-ttu-id="cb390-139">Selecione o **botão Excluir.**</span><span class="sxs-lookup"><span data-stu-id="cb390-139">Select the **Delete** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="cb390-140">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="cb390-140">Related topics</span></span>
- [<span data-ttu-id="cb390-141">Integração de dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="cb390-141">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="cb390-142">Servidores de integração</span><span class="sxs-lookup"><span data-stu-id="cb390-142">Onboard servers</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="cb390-143">Configurar configurações de conectividade de proxy e Internet</span><span class="sxs-lookup"><span data-stu-id="cb390-143">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="cb390-144">Solução de problemas de integração do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="cb390-144">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
