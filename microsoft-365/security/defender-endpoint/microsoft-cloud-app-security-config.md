---
title: Configurar a integração com o Microsoft Cloud App Security
ms.reviewer: ''
description: Saiba como ativar as configurações para habilitar a integração do Microsoft Defender for Endpoint com o Microsoft Cloud App Security.
keywords: nuvem, aplicativo, segurança, configurações, integração, descoberta, relatório
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
ms.openlocfilehash: f5e2919ae3fcbbb443f6d160c68633ee3427ae5a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187524"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="8676b-104">Configurar o Microsoft Cloud App Security no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="8676b-104">Configure Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8676b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="8676b-105">**Applies to:**</span></span>
- [<span data-ttu-id="8676b-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="8676b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8676b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8676b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8676b-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="8676b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8676b-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="8676b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="8676b-110">Para se beneficiar dos sinais de descoberta de aplicativos de nuvem do Microsoft Defender para Endpoint, a ligue a integração com o Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="8676b-110">To benefit from Microsoft Defender for Endpoint cloud app discovery signals, turn on Microsoft Cloud App Security integration.</span></span>

>[!NOTE]
><span data-ttu-id="8676b-111">Esse recurso estará disponível com uma licença E5 para [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) em dispositivos que executam o Windows 10, versão 1709 (Com build do sistema operacional 16299.1085 com [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, versão 1803 (build 17134.704 do sistema operacional com [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, versão 1809 (build 17763.379 do sistema operacional com [KB4489899](https://support.microsoft.com/help/4489899)) ou versões posteriores do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="8676b-111">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)) or later Windows 10 versions.</span></span>

> <span data-ttu-id="8676b-112">Consulte [Integração do Microsoft Defender para Ponto](https://docs.microsoft.com/cloud-app-security/mde-integration) de Extremidade com o Microsoft Cloud App Security para integração detalhada do Microsoft Defender para Ponto de Extremidade com o Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="8676b-112">See [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration) for detailed integration of Microsoft Defender for Endpoint with Microsoft Cloud App Security.</span></span> 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="8676b-113">Habilitar o Microsoft Cloud App Security no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="8676b-113">Enable Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="8676b-114">No painel de navegação, selecione **Configuração de preferências**  >  **Recursos avançados**.</span><span class="sxs-lookup"><span data-stu-id="8676b-114">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="8676b-115">Selecione **Microsoft Cloud App Security** e alterne a alternância para **On**.</span><span class="sxs-lookup"><span data-stu-id="8676b-115">Select **Microsoft Cloud App Security** and switch the toggle to **On**.</span></span>
3. <span data-ttu-id="8676b-116">Clique **em Salvar preferências**.</span><span class="sxs-lookup"><span data-stu-id="8676b-116">Click **Save preferences**.</span></span>

<span data-ttu-id="8676b-117">Depois de ativado, o Microsoft Defender para Ponto de Extremidade começará imediatamente a encaminhar sinais de descoberta para o Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="8676b-117">Once activated, Microsoft Defender for Endpoint will immediately start forwarding discovery signals to Cloud App Security.</span></span>

## <a name="view-the-data-collected"></a><span data-ttu-id="8676b-118">Exibir os dados coletados</span><span class="sxs-lookup"><span data-stu-id="8676b-118">View the data collected</span></span>

<span data-ttu-id="8676b-119">Para exibir e acessar dados do Microsoft Defender para Endpoint no Microsoft Cloud Apps Security, consulte [Investigar dispositivos em Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security).</span><span class="sxs-lookup"><span data-stu-id="8676b-119">To view and access Microsoft Defender for Endpoint data in Microsoft Cloud Apps Security, see [Investigate devices in Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security).</span></span>


<span data-ttu-id="8676b-120">Para obter mais informações sobre descoberta na nuvem, consulte [Trabalhando com aplicativos descobertos.](https://docs.microsoft.com/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="8676b-120">For more information about cloud discovery, see [Working with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>

<span data-ttu-id="8676b-121">Se você estiver interessado em tentar o Microsoft Cloud App Security, consulte [Microsoft Cloud App Security Trial](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1).</span><span class="sxs-lookup"><span data-stu-id="8676b-121">If you're interested in trying Microsoft Cloud App Security, see [Microsoft Cloud App Security Trial](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1).</span></span>

## <a name="related-topic"></a><span data-ttu-id="8676b-122">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8676b-122">Related topic</span></span>
- [<span data-ttu-id="8676b-123">Integração com o Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8676b-123">Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-integration.md)
