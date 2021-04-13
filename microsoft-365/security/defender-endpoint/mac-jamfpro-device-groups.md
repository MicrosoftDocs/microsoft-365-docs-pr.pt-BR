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
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a>Configurar o Microsoft Defender para Ponto de Extremidade em grupos de dispositivos macOS no Jamf Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Configurar os grupos de dispositivos semelhantes às OUs (organização de política de grupo), conjunto de dispositivos do Microsoft Endpoint Configuration Manager e grupos de dispositivos do Intune.

1. Navegue **até Grupos de Computadores Estáticos**.

2. Selecione **Novo**. 

    ![Imagem do Jamf Pro1](images/jamf-pro-static-group.png)

3. Forneça um nome de exibição e selecione **Salvar**.

    ![Imagem de Jamf Pro2](images/jamfpro-machine-group.png)

4. Agora você verá o Grupo de **Máquinas da Contoso** em **Grupos de Computadores Estáticos.**

    ![Imagem do Jamf Pro3](images/contoso-machine-group.png)

## <a name="next-step"></a>Próxima etapa
- [Configurar o Microsoft Defender para Ponto de Extremidade em políticas macOS no Jamf Pro](mac-jamfpro-policies.md)
