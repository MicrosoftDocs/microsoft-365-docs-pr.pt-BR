---
title: Configurar grupos de dispositivos no Jamf Pro
description: Saiba como configurar grupos de dispositivos no Jamf Pro para Microsoft Defender ATP para macOS
keywords: device, group, microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 6c1d6ae5d4635186bf0a1cbb55c7f906e8584f01
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689684"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a><span data-ttu-id="64322-104">Configurar o Microsoft Defender para Ponto de Extremidade em grupos de dispositivos macOS no Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="64322-104">Set up Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="64322-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="64322-105">**Applies to:**</span></span>
- [<span data-ttu-id="64322-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="64322-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="64322-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64322-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="64322-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="64322-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="64322-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="64322-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="64322-110">Configurar os grupos de dispositivos semelhantes às OUs (organização de política de grupo), conjunto de dispositivos do Microsoft Endpoint Configuration Manager e grupos de dispositivos do Intune.</span><span class="sxs-lookup"><span data-stu-id="64322-110">Set up the device groups similar to Group policy  organizational unite (OUs), Microsoft Endpoint Configuration Manager's device collection, and Intune's device groups.</span></span>

1. <span data-ttu-id="64322-111">Navegue **até Grupos de Computadores Estáticos**.</span><span class="sxs-lookup"><span data-stu-id="64322-111">Navigate to **Static Computer Groups**.</span></span>

2. <span data-ttu-id="64322-112">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="64322-112">Select **New**.</span></span> 

    ![Imagem do Jamf Pro1](images/jamf-pro-static-group.png)

3. <span data-ttu-id="64322-114">Forneça um nome de exibição e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="64322-114">Provide a display name and select **Save**.</span></span>

    ![Imagem de Jamf Pro2](images/jamfpro-machine-group.png)

4. <span data-ttu-id="64322-116">Agora você verá o Grupo de **Máquinas da Contoso** em **Grupos de Computadores Estáticos.**</span><span class="sxs-lookup"><span data-stu-id="64322-116">Now you will see the **Contoso's Machine Group** under **Static Computer Groups**.</span></span>

    ![Imagem do Jamf Pro3](images/contoso-machine-group.png)

## <a name="next-step"></a><span data-ttu-id="64322-118">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="64322-118">Next step</span></span>
- [<span data-ttu-id="64322-119">Configurar o Microsoft Defender para Ponto de Extremidade em políticas macOS no Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="64322-119">Set up Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
