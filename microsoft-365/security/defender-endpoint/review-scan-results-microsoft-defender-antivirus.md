---
title: Analisar os resultados das verificações do Microsoft Defender AV
description: Revise os resultados das verificações usando Microsoft Endpoint Configuration Manager, Microsoft Intune ou o Segurança do Windows app
keywords: resultados de verificação, correção, verificação completa, verificação rápida
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ec3dd2edc09d504af0ed76b17577130b1cdce1b7
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275367"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a><span data-ttu-id="38fa0-104">Examinar Microsoft Defender Antivírus resultados da verificação</span><span class="sxs-lookup"><span data-stu-id="38fa0-104">Review Microsoft Defender Antivirus scan results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="38fa0-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="38fa0-105">**Applies to:**</span></span>

- [<span data-ttu-id="38fa0-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="38fa0-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="38fa0-107">Depois que uma Microsoft Defender Antivírus de verificação for [](run-scan-microsoft-defender-antivirus.md) concluída, se for uma verificação sob demanda ou [agendada,](scheduled-catch-up-scans-microsoft-defender-antivirus.md)os resultados serão gravados e você poderá exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="38fa0-107">After a Microsoft Defender Antivirus scan completes, whether it is an [on-demand](run-scan-microsoft-defender-antivirus.md) or [scheduled scan](scheduled-catch-up-scans-microsoft-defender-antivirus.md), the results are recorded and you can view the results.</span></span> 


## <a name="use-configuration-manager-to-review-scan-results"></a><span data-ttu-id="38fa0-108">Usar o Configuration Manager para revisar os resultados da verificação</span><span class="sxs-lookup"><span data-stu-id="38fa0-108">Use Configuration Manager to review scan results</span></span>

<span data-ttu-id="38fa0-109">Consulte [Como monitorar o Endpoint Protection status](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span><span class="sxs-lookup"><span data-stu-id="38fa0-109">See [How to monitor Endpoint Protection status](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span>

## <a name="use-powershell-cmdlets-to-review-scan-results"></a><span data-ttu-id="38fa0-110">Usar cmdlets do PowerShell para revisar os resultados da verificação</span><span class="sxs-lookup"><span data-stu-id="38fa0-110">Use PowerShell cmdlets to review scan results</span></span>

<span data-ttu-id="38fa0-111">O cmdlet a seguir retornará cada detecção no ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="38fa0-111">The following cmdlet will return each detection on the endpoint.</span></span> <span data-ttu-id="38fa0-112">Se houver várias detecções da mesma ameaça, cada detecção será listada separadamente, com base no tempo de cada detecção:</span><span class="sxs-lookup"><span data-stu-id="38fa0-112">If there are multiple detections of the same threat, each detection will be listed separately, based on the time of each detection:</span></span>

```PowerShell
Get-MpThreatDetection
```

![captura de tela de cmdlets e saídas do PowerShell](images/defender/wdav-get-mpthreatdetection.png)

<span data-ttu-id="38fa0-114">Você pode especificar `-ThreatID` para limitar a saída para mostrar apenas as detecções de uma ameaça específica.</span><span class="sxs-lookup"><span data-stu-id="38fa0-114">You can specify `-ThreatID` to limit the output to only show the detections for a specific threat.</span></span>

<span data-ttu-id="38fa0-115">Se você quiser listar detecções de ameaças, mas combinar detecções da mesma ameaça em um único item, você pode usar o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="38fa0-115">If you want to list threat detections, but combine detections of the same threat into a single item, you can use the following cmdlet:</span></span>

```PowerShell
Get-MpThreat
```

![captura de tela do PowerShell](images/defender/wdav-get-mpthreat.png)

<span data-ttu-id="38fa0-117">Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/) Microsoft Defender Antivírus e Defender para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="38fa0-117">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a><span data-ttu-id="38fa0-118">Use Windows Instrução de Gerenciamento (WMI) para revisar os resultados da verificação</span><span class="sxs-lookup"><span data-stu-id="38fa0-118">Use Windows Management Instruction (WMI) to review scan results</span></span>

<span data-ttu-id="38fa0-119">Use o [ **método Get** das **classes MSFT_MpThreat** e **MSFT_MpThreatDetection.**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="38fa0-119">Use the [**Get** method of the **MSFT_MpThreat** and **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) classes.</span></span>


## <a name="related-articles"></a><span data-ttu-id="38fa0-120">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="38fa0-120">Related articles</span></span>

- [<span data-ttu-id="38fa0-121">Personalizar, iniciar e revisar os resultados de Microsoft Defender Antivírus e correção</span><span class="sxs-lookup"><span data-stu-id="38fa0-121">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="38fa0-122">Microsoft Defender Antivírus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="38fa0-122">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)