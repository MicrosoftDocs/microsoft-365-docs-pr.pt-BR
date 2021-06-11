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
# <a name="schedule-antivirus-scans-using-powershell"></a><span data-ttu-id="d3323-104">Agendar verificações antivírus usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3323-104">Schedule antivirus scans using PowerShell</span></span>

<span data-ttu-id="d3323-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d3323-105">**Applies to:**</span></span>

- [<span data-ttu-id="d3323-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d3323-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="d3323-107">Este artigo descreve como configurar verificações agendadas usando cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3323-107">This article describes how to configure scheduled scans using PowerShell cmdlets.</span></span> <span data-ttu-id="d3323-108">Para saber mais sobre o agendamento de verificações e sobre tipos de verificação, consulte [Configure scheduled quick or full Microsoft Defender Antivírus scans](schedule-antivirus-scans.md).</span><span class="sxs-lookup"><span data-stu-id="d3323-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="d3323-109">Usar cmdlets do PowerShell para agendar verificações</span><span class="sxs-lookup"><span data-stu-id="d3323-109">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="d3323-110">Use os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="d3323-110">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="d3323-111">Para obter mais informações, consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/) Microsoft Defender Antivírus e Defender para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="d3323-111">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="d3323-112">Cmdlets do PowerShell para agendamento de verificações quando um ponto de extremidade não está em uso</span><span class="sxs-lookup"><span data-stu-id="d3323-112">PowerShell cmdlets for scheduling scans when an endpoint is not in use</span></span>

<span data-ttu-id="d3323-113">Use os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="d3323-113">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="d3323-114">Para obter mais informações, confira [Usar cmdlets do PowerShell para configurar e executar o Microsoft Defender Antivírus](use-powershell-cmdlets-microsoft-defender-antivirus.md) e [cmdlets do Defender](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="d3323-114">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

> [!NOTE]
> <span data-ttu-id="d3323-115">Quando você agenda verifica os horários em que os pontos de extremidade não estão em uso, as verificações não honram a configuração de interrupção da CPU e aproveitam totalmente os recursos disponíveis para concluir a verificação o mais rápido possível.</span><span class="sxs-lookup"><span data-stu-id="d3323-115">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a><span data-ttu-id="d3323-116">Cmdlets do PowerShell para agendamento de verificações para concluir a correção</span><span class="sxs-lookup"><span data-stu-id="d3323-116">PowerShell cmdlets for scheduling scans to complete remediation</span></span>

<span data-ttu-id="d3323-117">Use os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="d3323-117">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="d3323-118">Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/) Microsoft Defender Antivírus e Defender para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="d3323-118">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a><span data-ttu-id="d3323-119">Cmdlets do PowerShell para agendar verificações diárias</span><span class="sxs-lookup"><span data-stu-id="d3323-119">PowerShell cmdlets for scheduling daily scans</span></span>

<span data-ttu-id="d3323-120">Use os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="d3323-120">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="d3323-121">Para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus, consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/)Microsoft Defender Antivírus e Defender.</span><span class="sxs-lookup"><span data-stu-id="d3323-121">For more information about how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>


