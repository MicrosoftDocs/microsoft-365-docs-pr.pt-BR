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
# <a name="review-microsoft-defender-antivirus-scan-results"></a>Examinar Microsoft Defender Antivírus resultados da verificação

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Depois que uma Microsoft Defender Antivírus de verificação for [](run-scan-microsoft-defender-antivirus.md) concluída, se for uma verificação sob demanda ou [agendada,](scheduled-catch-up-scans-microsoft-defender-antivirus.md)os resultados serão gravados e você poderá exibir os resultados. 


## <a name="use-configuration-manager-to-review-scan-results"></a>Usar o Configuration Manager para revisar os resultados da verificação

Consulte [Como monitorar o Endpoint Protection status](/configmgr/protect/deploy-use/monitor-endpoint-protection).

## <a name="use-powershell-cmdlets-to-review-scan-results"></a>Usar cmdlets do PowerShell para revisar os resultados da verificação

O cmdlet a seguir retornará cada detecção no ponto de extremidade. Se houver várias detecções da mesma ameaça, cada detecção será listada separadamente, com base no tempo de cada detecção:

```PowerShell
Get-MpThreatDetection
```

![captura de tela de cmdlets e saídas do PowerShell](images/defender/wdav-get-mpthreatdetection.png)

Você pode especificar `-ThreatID` para limitar a saída para mostrar apenas as detecções de uma ameaça específica.

Se você quiser listar detecções de ameaças, mas combinar detecções da mesma ameaça em um único item, você pode usar o seguinte cmdlet:

```PowerShell
Get-MpThreat
```

![captura de tela do PowerShell](images/defender/wdav-get-mpthreat.png)

Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/) Microsoft Defender Antivírus e Defender para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus.

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a>Use Windows Instrução de Gerenciamento (WMI) para revisar os resultados da verificação

Use o [ **método Get** das **classes MSFT_MpThreat** e **MSFT_MpThreatDetection.**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a>Artigos relacionados

- [Personalizar, iniciar e revisar os resultados de Microsoft Defender Antivírus e correção](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)