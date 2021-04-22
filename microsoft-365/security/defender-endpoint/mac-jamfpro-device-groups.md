---
title: Configurar grupos de dispositivos no Jamf Pro
description: Saiba como configurar grupos de dispositivos no Jamf Pro para Microsoft Defender para Ponto de Extremidade no macOS
keywords: device, group, microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 772b67ec84ae9614c9322763c140a60e7884644d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933800"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a><span data-ttu-id="c3671-104">Configurar o Microsoft Defender para Ponto de Extremidade em grupos de dispositivos macOS no Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="c3671-104">Set up Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c3671-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c3671-105">**Applies to:**</span></span>
- [<span data-ttu-id="c3671-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c3671-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c3671-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3671-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c3671-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="c3671-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c3671-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="c3671-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="c3671-110">Configurar os grupos de dispositivos semelhantes às OUs (organização de política de grupo), conjunto de dispositivos do Microsoft Endpoint Configuration Manager e grupos de dispositivos do Intune.</span><span class="sxs-lookup"><span data-stu-id="c3671-110">Set up the device groups similar to Group policy  organizational unite (OUs), Microsoft Endpoint Configuration Manager's device collection, and Intune's device groups.</span></span>

1. <span data-ttu-id="c3671-111">Navegue **até Grupos de Computadores Estáticos**.</span><span class="sxs-lookup"><span data-stu-id="c3671-111">Navigate to **Static Computer Groups**.</span></span>

2. <span data-ttu-id="c3671-112">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c3671-112">Select **New**.</span></span> 

    ![Imagem do Jamf Pro1](images/jamf-pro-static-group.png)

3. <span data-ttu-id="c3671-114">Forneça um nome de exibição e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c3671-114">Provide a display name and select **Save**.</span></span>

    ![Imagem de Jamf Pro2](images/jamfpro-machine-group.png)

4. <span data-ttu-id="c3671-116">Agora você verá o Grupo de **Máquinas da Contoso** em **Grupos de Computadores Estáticos.**</span><span class="sxs-lookup"><span data-stu-id="c3671-116">Now you will see the **Contoso's Machine Group** under **Static Computer Groups**.</span></span>

    ![Imagem do Jamf Pro3](images/contoso-machine-group.png)

## <a name="next-step"></a><span data-ttu-id="c3671-118">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="c3671-118">Next step</span></span>
- [<span data-ttu-id="c3671-119">Configurar o Microsoft Defender para Ponto de Extremidade em políticas macOS no Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="c3671-119">Set up Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
