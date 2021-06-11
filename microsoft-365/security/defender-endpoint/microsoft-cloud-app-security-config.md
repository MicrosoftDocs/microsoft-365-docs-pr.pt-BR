---
title: Configurar a integração do Microsoft Cloud App Security
ms.reviewer: ''
description: Saiba como ativar as configurações para habilitar a integração do Microsoft Defender for Endpoint com Microsoft Cloud App Security.
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
ms.openlocfilehash: 4f7aca5cb532510d55042c70d04d65f2aa08baa3
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844749"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="16d40-104">Configurar Microsoft Cloud App Security no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="16d40-104">Configure Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="16d40-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="16d40-105">**Applies to:**</span></span>
- [<span data-ttu-id="16d40-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="16d40-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="16d40-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16d40-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="16d40-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="16d40-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="16d40-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="16d40-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="16d40-110">Para se beneficiar dos sinais de descoberta de aplicativos de nuvem do Microsoft Defender para Endpoint, a Microsoft Cloud App Security integração.</span><span class="sxs-lookup"><span data-stu-id="16d40-110">To benefit from Microsoft Defender for Endpoint cloud app discovery signals, turn on Microsoft Cloud App Security integration.</span></span>

>[!NOTE]
><span data-ttu-id="16d40-111">Esse recurso estará disponível com uma [](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) licença E5 para Enterprise Mobility + Security em dispositivos que executam o Windows 10, versão 1709 (Com build do sistema operacional 16299.1085 com [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, versão 1803 (Build 17134.704 com [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, versão 1809 (build 17763.379 do sistema operacional com [KB4489899](https://support.microsoft.com/help/4489899)) ou posterior Windows 10 versões.</span><span class="sxs-lookup"><span data-stu-id="16d40-111">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)) or later Windows 10 versions.</span></span>

> <span data-ttu-id="16d40-112">Consulte [Integração do Microsoft Defender para Ponto](/cloud-app-security/mde-integration) de Extremidade com Microsoft Cloud App Security para integração detalhada do Microsoft Defender para Ponto de Extremidade com Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="16d40-112">See [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration) for detailed integration of Microsoft Defender for Endpoint with Microsoft Cloud App Security.</span></span> 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="16d40-113">Habilitar Microsoft Cloud App Security no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="16d40-113">Enable Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="16d40-114">No painel de navegação, selecione **Configuração de preferências**  >  **Recursos avançados**.</span><span class="sxs-lookup"><span data-stu-id="16d40-114">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="16d40-115">Selecione **Microsoft Cloud App Security** e alterne a alternância para **On**.</span><span class="sxs-lookup"><span data-stu-id="16d40-115">Select **Microsoft Cloud App Security** and switch the toggle to **On**.</span></span>
3. <span data-ttu-id="16d40-116">Clique **em Salvar preferências**.</span><span class="sxs-lookup"><span data-stu-id="16d40-116">Click **Save preferences**.</span></span>

<span data-ttu-id="16d40-117">Depois de ativado, o Microsoft Defender para Ponto de Extremidade começará imediatamente a encaminhar sinais de descoberta para Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="16d40-117">Once activated, Microsoft Defender for Endpoint will immediately start forwarding discovery signals to Cloud App Security.</span></span>

## <a name="view-the-data-collected"></a><span data-ttu-id="16d40-118">Exibir os dados coletados</span><span class="sxs-lookup"><span data-stu-id="16d40-118">View the data collected</span></span>

<span data-ttu-id="16d40-119">Para exibir e acessar dados do Microsoft Defender for Endpoint no Microsoft Cloud Apps Security, consulte [Investigar dispositivos em Cloud App Security](/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security).</span><span class="sxs-lookup"><span data-stu-id="16d40-119">To view and access Microsoft Defender for Endpoint data in Microsoft Cloud Apps Security, see [Investigate devices in Cloud App Security](/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security).</span></span>


<span data-ttu-id="16d40-120">Para obter mais informações sobre descoberta na nuvem, consulte [Trabalhando com aplicativos descobertos.](/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="16d40-120">For more information about cloud discovery, see [Working with discovered apps](/cloud-app-security/discovered-apps).</span></span>

<span data-ttu-id="16d40-121">Se você estiver interessado em tentar Microsoft Cloud App Security, consulte [Microsoft Cloud App Security Trial](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1).</span><span class="sxs-lookup"><span data-stu-id="16d40-121">If you're interested in trying Microsoft Cloud App Security, see [Microsoft Cloud App Security Trial](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1).</span></span>

## <a name="related-topic"></a><span data-ttu-id="16d40-122">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="16d40-122">Related topic</span></span>
- [<span data-ttu-id="16d40-123">Microsoft Cloud App Security integração</span><span class="sxs-lookup"><span data-stu-id="16d40-123">Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-integration.md)
