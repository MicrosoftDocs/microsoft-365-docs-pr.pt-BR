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
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a><span data-ttu-id="c5d46-104">Agendar verificações antivírus usando Windows Instrumentação de Gerenciamento (WMI)</span><span class="sxs-lookup"><span data-stu-id="c5d46-104">Schedule antivirus scans using Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="c5d46-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c5d46-105">**Applies to:**</span></span>

- [<span data-ttu-id="c5d46-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c5d46-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="c5d46-107">Este artigo descreve como configurar verificações agendadas usando o WMI.</span><span class="sxs-lookup"><span data-stu-id="c5d46-107">This article describes how to configure scheduled scans using WMI.</span></span> <span data-ttu-id="c5d46-108">Para saber mais sobre o agendamento de verificações e sobre tipos de verificação, consulte [Configure scheduled quick or full Microsoft Defender Antivírus scans](schedule-antivirus-scans.md).</span><span class="sxs-lookup"><span data-stu-id="c5d46-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="c5d46-109">Use Windows Instrução de Gerenciamento (WMI) para agendar verificações</span><span class="sxs-lookup"><span data-stu-id="c5d46-109">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="c5d46-110">Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="c5d46-110">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="c5d46-111">Para obter mais informações e parâmetros permitidos, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="c5d46-111">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="c5d46-112">WMI para agendar verificações quando um ponto de extremidade não está em uso</span><span class="sxs-lookup"><span data-stu-id="c5d46-112">WMI for scheduling scans when an endpoint is not in use</span></span>

<span data-ttu-id="c5d46-113">Use o [método Set da classe MSFT_MpPreference para](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="c5d46-113">Use the [Set method of the MSFT_MpPreference class](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="c5d46-114">Para obter mais informações sobre APIs e parâmetros permitidos, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="c5d46-114">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

> [!NOTE]
> <span data-ttu-id="c5d46-115">Quando você agenda verifica os horários em que os pontos de extremidade não estão em uso, as verificações não honram a configuração de interrupção da CPU e aproveitam totalmente os recursos disponíveis para concluir a verificação o mais rápido possível.</span><span class="sxs-lookup"><span data-stu-id="c5d46-115">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a><span data-ttu-id="c5d46-116">WMI para agendar verificações para concluir a correção</span><span class="sxs-lookup"><span data-stu-id="c5d46-116">WMI for scheduling scans to complete remediation</span></span>

<span data-ttu-id="c5d46-117">Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="c5d46-117">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="c5d46-118">Para obter mais informações e parâmetros permitidos, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="c5d46-118">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="wmi-for-scheduling-daily-scans"></a><span data-ttu-id="c5d46-119">WMI para agendar verificações diárias</span><span class="sxs-lookup"><span data-stu-id="c5d46-119">WMI for scheduling daily scans</span></span>

<span data-ttu-id="c5d46-120">Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="c5d46-120">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="c5d46-121">Para obter mais informações e parâmetros permitidos, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="c5d46-121">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

