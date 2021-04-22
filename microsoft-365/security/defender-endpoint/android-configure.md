---
title: Configurar o Microsoft Defender para Ponto de Extremidade para recursos do Android
description: Descreve como configurar o Microsoft Defender para Ponto de Extremidade no Android
keywords: microsoft, defender, Microsoft Defender for Endpoint, mde, android, configuration
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 462fa6177ee35d5d988efa985422b499e2339ff4
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935312"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a>Configurar o Defender para Ponto de Extremidade em recursos do Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a>Acesso condicional com o Defender para Ponto de Extremidade no Android  
O Microsoft Defender para Ponto de Extremidade no Android juntamente com o Microsoft Intune e o Azure Active Directory permite a imposição de políticas de conformidade de dispositivo e acesso condicional com base nos níveis de risco do dispositivo. O Defender for Endpoint é uma solução MTD (Mobile Threat Defense) que você pode implantar para aproveitar esse recurso por meio do Intune.

Para obter mais informações sobre como configurar o Defender para Ponto de Extremidade no Android e no Acesso Condicional, consulte [Defender for Endpoint e Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).

## <a name="configure-custom-indicators"></a>Configurar indicadores personalizados  

> [!NOTE]
> O Defender para Ponto de Extremidade no Android só dá suporte à criação de indicadores personalizados para endereços IP e URLs/domínios.

O Defender para Ponto de Extremidade no Android permite que os administradores configurem indicadores personalizados para dar suporte a dispositivos Android também. Para obter mais informações sobre como configurar indicadores personalizados, consulte [Manage indicators](manage-indicators.md).

## <a name="configure-web-protection"></a>Configurar a proteção da Web
O Defender para Ponto de Extremidade no Android permite aos administradores de IT a capacidade de configurar o recurso de proteção da Web. Esse recurso está disponível no Centro de Administração do Microsoft Endpoint Manager.

> [!NOTE]
> O Defender para Ponto de Extremidade no Android usaria uma VPN para fornecer o recurso de Proteção da Web. Esta não é uma VPN regular e é uma VPN local/auto-loop que não faz o tráfego fora do dispositivo. Para obter mais informações, consulte [Configure Web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral do Microsoft Defender para Ponto de Extremidade para Android](microsoft-defender-endpoint-android.md)
- [Implantar o Microsoft Defender para Ponto de Extremidade para Android com o Microsoft Intune](android-intune.md)
