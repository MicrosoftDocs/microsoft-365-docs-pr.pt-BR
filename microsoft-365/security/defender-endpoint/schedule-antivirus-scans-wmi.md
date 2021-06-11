---
title: Agendar verificações antivírus usando Windows Instrumentação de Gerenciamento
description: Agendar verificações antivírus usando o WMI
keywords: verificação rápida, verificação completa, WMI, agendamento, antivírus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 1aa174f4601fb57eebbc4fb7c78e1809b9f072c8
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879640"
---
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a>Agendar verificações antivírus usando Windows Instrumentação de Gerenciamento (WMI)

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Este artigo descreve como configurar verificações agendadas usando o WMI. Para saber mais sobre o agendamento de verificações e sobre tipos de verificação, consulte [Configure scheduled quick or full Microsoft Defender Antivírus scans](schedule-antivirus-scans.md). 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>Use Windows Instrução de Gerenciamento (WMI) para agendar verificações

Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

Para obter mais informações e parâmetros permitidos, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>WMI para agendar verificações quando um ponto de extremidade não está em uso

Use o [método Set da classe MSFT_MpPreference para](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) as seguintes propriedades:

```WMI
ScanOnlyIfIdleEnabled
```

Para obter mais informações sobre APIs e parâmetros permitidos, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

> [!NOTE]
> Quando você agenda verifica os horários em que os pontos de extremidade não estão em uso, as verificações não honram a configuração de interrupção da CPU e aproveitam totalmente os recursos disponíveis para concluir a verificação o mais rápido possível.


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a>WMI para agendar verificações para concluir a correção

Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

Para obter mais informações e parâmetros permitidos, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

## <a name="wmi-for-scheduling-daily-scans"></a>WMI para agendar verificações diárias

Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:

```WMI
ScanScheduleQuickScanTime
```

Para obter mais informações e parâmetros permitidos, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

