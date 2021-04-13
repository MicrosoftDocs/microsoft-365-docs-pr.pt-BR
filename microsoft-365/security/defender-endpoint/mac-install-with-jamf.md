---
title: Implantando o Microsoft Defender ATP para macOS com o Jamf Pro
description: Implantando o Microsoft Defender ATP para macOS com o Jamf Pro
keywords: microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a8015221f26250451a6cbcab8e66f35aafdc0767
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689699"
---
# <a name="deploying-microsoft-defender-for-endpoint-on-macos-with-jamf-pro"></a><span data-ttu-id="a4913-104">Implantando o Microsoft Defender para Ponto de Extremidade no macOS com o Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="a4913-104">Deploying Microsoft Defender for Endpoint on macOS with Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a4913-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="a4913-105">**Applies to:**</span></span>
- [<span data-ttu-id="a4913-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="a4913-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a4913-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a4913-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a4913-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="a4913-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a4913-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="a4913-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="a4913-110">Saiba como implantar o Microsoft Defender para Ponto de Extremidade no macOS com o Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="a4913-110">Learn how to deploy Microsoft Defender for Endpoint on macOS with Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="a4913-111">Se você estiver usando macOS Catalina (10.15.4) ou versões mais recentes do macOS, consulte Novos perfis de configuração para [macOS Catalina](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies)e versões mais recentes do macOS .</span><span class="sxs-lookup"><span data-stu-id="a4913-111">If you are using macOS Catalina (10.15.4) or newer versions of macOS, see [New configuration profiles for macOS Catalina and newer versions of macOS](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies).</span></span>

<span data-ttu-id="a4913-112">Este é um processo de várias etapas.</span><span class="sxs-lookup"><span data-stu-id="a4913-112">This is a multi step process.</span></span> <span data-ttu-id="a4913-113">Você precisará concluir todas as etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="a4913-113">You'll need to complete all of the following steps:</span></span>

- [<span data-ttu-id="a4913-114">Faça logon no Portal jamf</span><span class="sxs-lookup"><span data-stu-id="a4913-114">Login to the Jamf Portal</span></span>](mac-install-jamfpro-login.md)
- [<span data-ttu-id="a4913-115">Configurar o Microsoft Defender para Ponto de Extremidade em grupos de dispositivos macOS no Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="a4913-115">Setup the Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>](mac-jamfpro-device-groups.md)
- [<span data-ttu-id="a4913-116">Configurar o Microsoft Defender para Ponto de Extremidade em políticas macOS no Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="a4913-116">Setup the Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
- [<span data-ttu-id="a4913-117">Registrar o Microsoft Defender para Ponto de Extremidade em dispositivos macOS no Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="a4913-117">Enroll the Microsoft Defender for Endpoint on macOS devices into Jamf Pro</span></span>](mac-jamfpro-enroll-devices.md)




