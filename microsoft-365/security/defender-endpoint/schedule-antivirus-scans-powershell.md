---
title: Agendar verificações antivírus usando o PowerShell
description: Agendar verificações antivírus usando o PowerShell
keywords: verificação rápida, verificação completa, antivírus, agendamento, PowerShell
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
ms.openlocfilehash: 73ba654dd312c63651f0cf43244796e94e8ad55b
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879641"
---
# <a name="schedule-antivirus-scans-using-powershell"></a>Agendar verificações antivírus usando o PowerShell

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Este artigo descreve como configurar verificações agendadas usando cmdlets do PowerShell. Para saber mais sobre o agendamento de verificações e sobre tipos de verificação, consulte [Configure scheduled quick or full Microsoft Defender Antivírus scans](schedule-antivirus-scans.md). 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a>Usar cmdlets do PowerShell para agendar verificações

Use os seguintes cmdlets:

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

Para obter mais informações, consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/) Microsoft Defender Antivírus e Defender para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus.

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>Cmdlets do PowerShell para agendamento de verificações quando um ponto de extremidade não está em uso

Use os seguintes cmdlets:

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

Para obter mais informações, confira [Usar cmdlets do PowerShell para configurar e executar o Microsoft Defender Antivírus](use-powershell-cmdlets-microsoft-defender-antivirus.md) e [cmdlets do Defender](/powershell/module/defender/).

> [!NOTE]
> Quando você agenda verifica os horários em que os pontos de extremidade não estão em uso, as verificações não honram a configuração de interrupção da CPU e aproveitam totalmente os recursos disponíveis para concluir a verificação o mais rápido possível.

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a>Cmdlets do PowerShell para agendamento de verificações para concluir a correção

Use os seguintes cmdlets:

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/) Microsoft Defender Antivírus e Defender para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus.

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a>Cmdlets do PowerShell para agendar verificações diárias

Use os seguintes cmdlets:

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

Para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus, consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/)Microsoft Defender Antivírus e Defender.


