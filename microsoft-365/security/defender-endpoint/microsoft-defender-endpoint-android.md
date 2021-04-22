---
title: Microsoft Defender para Ponto de Extremidade para Android
ms.reviewer: ''
description: Descreve como instalar e usar o Microsoft Defender para Ponto de Extremidade no Android
keywords: microsoft, defender, Microsoft Defender for Endpoint, android, installation, deploy, uninstallation, intune
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
ms.openlocfilehash: 35a43aa7bfcd9ed8c83d10c2ec44a974b03bca72
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935564"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a>Microsoft Defender para Ponto de Extremidade para Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Este tópico descreve como instalar, configurar, atualizar e usar o Defender para Ponto de Extremidade no Android.

> [!CAUTION]
> A execução de outros produtos de proteção de ponto de extremidade de terceiros juntamente com o Defender for Endpoint no Android provavelmente causará problemas de desempenho e erros imprevisíveis do sistema.


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a>Como instalar o Microsoft Defender para Ponto de Extremidade no Android

### <a name="prerequisites"></a>Pré-requisitos

-   **Para usuários finais**

    -   Licença do Microsoft Defender para Ponto de Extremidade atribuída ao(s) usuário(s) final do aplicativo. Consulte [Requisitos de licenciamento](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements) do Microsoft Defender para Ponto de Extremidade

    -   O aplicativo do Portal da Empresa do Intune pode ser baixado no [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) e está disponível no dispositivo Android.

        -   Além disso, os dispositivos podem [ser](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) inscritos por meio do aplicativo Portal da Empresa do Intune para impor políticas de conformidade de dispositivos do Intune. Isso exige que o usuário final seja atribuído a uma licença do Microsoft Intune.

    -   Para obter mais informações sobre como atribuir licenças, consulte [Atribuir licenças aos usuários](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).
        

-   **Para administradores**

    -   Acesso ao portal do Centro de Segurança do Microsoft Defender.

        > [!NOTE]
        > O Microsoft Intune é a única solução MDM (Gerenciamento de Dispositivo Móvel) com suporte para implantar o Microsoft Defender para Ponto de Extremidade no Android. Atualmente, apenas dispositivos inscritos têm suporte para impor o Defender for Endpoint em políticas de conformidade de dispositivos relacionados ao Android no Intune. 

    -   Acesse [o Centro de administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), para implantar o aplicativo em grupos de usuários inscritos em sua organização.

### <a name="system-requirements"></a>Requisitos do sistema

-   Dispositivos Android executando o Android 6.0 e superior.
-   O aplicativo do Portal da Empresa do Intune é baixado do [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) e instalado. O registro de dispositivo é necessário para que as políticas de conformidade do dispositivo Intune sejam impostas.

### <a name="installation-instructions"></a>Instruções de instalação

O Microsoft Defender para Ponto de Extremidade no Android dá suporte à instalação em ambos os modos de dispositivos inscritos - os modos herdados Administrador de Dispositivos e Android Enterprise.
**Atualmente, dispositivos de propriedade pessoal com perfil de trabalho e registro de dispositivos de usuário totalmente gerenciados de propriedade corporativa são suportados no Android Enterprise. O suporte para outros modos Android Enterprise será anunciado quando estiver pronto.**

A implantação do Microsoft Defender para Ponto de Extremidade no Android é via Microsoft Intune (MDM).
Para obter mais informações, [consulte Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune](android-intune.md).


> [!NOTE]
> **O Microsoft Defender para Ponto de Extremidade no Android está disponível [no Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) agora.** <br> Você pode se conectar ao Google Play do Intune para implantar o microsoft Defender para aplicativo de ponto de extremidade, em modos de entrolamento do Administrador de Dispositivos e Android Enterprise. 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a>Como configurar o Microsoft Defender para Ponto de Extremidade no Android

As diretrizes sobre como configurar o Microsoft Defender para Ponto de Extremidade em recursos android estão disponíveis em [Configure Microsoft Defender for Endpoint on Android features](android-configure.md).



## <a name="related-topics"></a>Tópicos relacionados
- [Implantar o Microsoft Defender para Ponto de Extremidade para Android com o Microsoft Intune](android-intune.md)
- [Configurar o Microsoft Defender para Ponto de Extremidade para recursos do Android](android-configure.md)

