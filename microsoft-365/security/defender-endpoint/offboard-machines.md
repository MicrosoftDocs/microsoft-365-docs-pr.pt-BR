---
title: Dispositivos offboard do serviço Microsoft Defender ATP
description: Onboard Windows 10 devices, servers, non-Windows devices from the Microsoft Defender ATP service
keywords: offboarding, microsoft defender for endpoint offboarding, windows atp offboarding
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4a95ff5214ea9f696622ea184ece1c5aa9fb3db2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186960"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a>Dispositivos offboard do serviço Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plataformas**
- macOS
- Linux
- Windows Server 2012 R2
- Windows Server 2016

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-offboarddevices-abovefoldlink)

Siga as instruções correspondentes, dependendo do método de implantação preferencial.

>[!NOTE]
> O status de um dispositivo será alternado para [Inativo](fix-unhealthy-sensors.md#inactive-devices) 7 dias após o offboard. <br> Os dados dos dispositivos de fora (como Linha do Tempo, Alertas, Vulnerabilidades etc.) permanecerão no portal até que o período de retenção configurado [expire.](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) <br>
> O perfil do dispositivo (sem dados) [](machines-view-overview.md) permanecerá na Lista de Dispositivos por não mais de 180 dias.
> Além disso, os dispositivos que não estão ativos nos últimos 30 dias não são fatorados [](tvm-exposure-score.md) nos dados que refletem a pontuação de exposição a ameaças e vulnerabilidades da sua organização e a Pontuação Segura da Microsoft para Dispositivos. <br>
> Para exibir somente dispositivos ativos, você pode filtrar por estado de [saúde,](machines-view-overview.md#health-state)marcas [de dispositivo](machine-tags.md) ou grupos [de máquinas.](machine-groups.md) 

## <a name="offboard-windows-10-devices"></a>Offboard dispositivos Windows 10
- [Dispositivos offboard usando um script local](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [Dispositivos offboard usando a Política de Grupo](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [Dispositivos offboard usando ferramentas de Gerenciamento de Dispositivo Móvel](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a>Servidores offboard
- [Servidores offboard](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a>Offboard de dispositivos que não são windows
- [Offboard de dispositivos que não são windows](configure-endpoints-non-windows.md#offboard-non-windows-devices)

