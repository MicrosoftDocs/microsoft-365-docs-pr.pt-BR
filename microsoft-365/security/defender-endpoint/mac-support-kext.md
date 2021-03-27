---
title: Solucionar problemas de extensão de kernel no Microsoft Defender para Ponto de Extremidade para Mac
description: Solucionar problemas relacionados a extensões de kernel no Microsoft Defender para Endpoint para Mac.
keywords: microsoft, defender, atp, mac, kernel, extension
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
ms.openlocfilehash: 877cc619d3ba048cdf6ecc8149f073461d9eac8e
ms.sourcegitcommit: a965c498e6b3890877f895d5197898b306092813
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51379497"
---
# <a name="troubleshoot-kernel-extension-issues-in-microsoft-defender-for-endpoint-for-mac"></a>Solucionar problemas de extensão de kernel no Microsoft Defender para Ponto de Extremidade para Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade para Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Este artigo fornece informações sobre como solucionar problemas com a extensão do kernel instalada como parte do Microsoft Defender para Ponto de Extremidade para Mac.

A partir do macOS High Sierra (10.13), o macOS exige que todas as extensões de kernel sejam aprovadas explicitamente antes que elas sejam permitidas para execução no dispositivo.

Se você não aprovou a extensão do kernel durante a implantação/instalação do Microsoft Defender para Ponto de Extremidade para Mac, o aplicativo exibirá uma faixa solicitando que você habilita-lo:

   ![Captura de tela desabilitada de RTP](images/mdatp-32-main-app-fix.png)

Você também pode executar ```mdatp health``` . Ele relata se a proteção em tempo real está habilitada, mas não está disponível. Isso indica que a extensão do kernel não foi aprovada para ser executado em seu dispositivo.

```bash
mdatp health
```
```Output
...
real_time_protection_enabled                : false
real_time_protection_available              : true
...
```

As seções a seguir fornecem orientações sobre como resolver esse problema, dependendo do método usado para implantar o Microsoft Defender para Ponto de Extremidade para Mac.

## <a name="managed-deployment"></a>Implantação gerenciada

Consulte as instruções correspondentes à ferramenta de gerenciamento que você usou para implantar o produto:

- [Implantação baseada em JAMF](mac-install-with-jamf.md)
- [Implantação baseada no Microsoft Intune](mac-install-with-intune.md#create-system-configuration-profiles)

## <a name="manual-deployment"></a>Implantação manual

Se menos de 30 minutos se passaram desde que o produto foi instalado, navegue até System **Preferences** Security & Privacidade , onde você deve Permitir software do sistema dos desenvolvedores  >  "Microsoft  Corporation".

Se você não vir esse prompt, isso significa que 30 ou mais minutos passaram e a extensão do kernel ainda não foi aprovada para ser executado em seu dispositivo:

![Janela de segurança e privacidade após a captura de tela expirada do prompt](images/mdatp-33-securityprivacysettings-noprompt.png)

Nesse caso, você precisa executar as etapas a seguir para disparar o fluxo de aprovação novamente.

1. No Terminal, tente instalar o driver. A operação a seguir falhará, pois a extensão do kernel não foi aprovada para ser executado no dispositivo. No entanto, ele disparará o fluxo de aprovação novamente.

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```
    
    ```Output
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Diagnostics for /Library/Extensions/wdavkext.kext:
    ```

2. Abra **a Segurança de Preferências** do Sistema &  >  **Privacidade** no menu. (Feche-o primeiro, se estiver aberto.)

3. **Permitir** software do sistema de desenvolvedores "Microsoft Corporation"

4. No Terminal, instale o driver novamente. Desta vez, a operação terá êxito:

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```

    O banner deve desaparecer do aplicativo Defender e agora deve relatar que a proteção em tempo real está ```mdatp health``` habilitada e disponível:

    ```bash
    mdatp health
    ```

    ```Output
    ...
    real_time_protection_enabled                : true
    real_time_protection_available              : true
    ...
    ```
