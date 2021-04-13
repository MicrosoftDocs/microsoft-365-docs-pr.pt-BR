---
title: Monitorar e relatar sobre a proteção do Microsoft Defender Antivírus
description: Use o Configuration Manager ou as ferramentas de gerenciamento de eventos e informações de segurança (SIEM) para consumir relatórios e monitorar o Microsoft Defender AV com o PowerShell e o WMI.
keywords: siem, monitor, report, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f0065792f525827ccd1471087b8a707989ef61ef
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689894"
---
# <a name="report-on-microsoft-defender-antivirus"></a>Relatório sobre o Microsoft Defender Antivírus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

O Microsoft Defender Antivírus é integrado ao Windows 10, Windows Server 2019 e Windows Server 2016. O Microsoft Defender Antivírus é da sua proteção de última geração no Microsoft Defender para Ponto de Extremidade. A proteção de última geração ajuda a proteger seus dispositivos contra ameaças de software, como vírus, malware e spyware em email, aplicativos, nuvem e Web.

Com o Microsoft Defender Antivírus, você tem várias opções para revisar o status e os alertas de proteção. Você pode usar o Microsoft Endpoint Manager para [monitorar o Microsoft Defender Antivírus](/configmgr/protect/deploy-use/monitor-endpoint-protection) ou criar [alertas de email.](/configmgr/protect/deploy-use/endpoint-configure-alerts) Ou você pode monitorar a proteção usando [o Microsoft Intune](/intune/introduction-intune).  

O Microsoft Operations Management Suite tem um complemento de [Conformidade](/windows/deployment/update/update-compliance-get-started) de Atualização que relata os principais problemas do Microsoft Defender Antivírus, incluindo atualizações de proteção e configurações de proteção em tempo real.

Se você tiver um servidor siem (gerenciamento de eventos) e informações de segurança de terceiros, você também poderá consumir Windows Defender [eventos de cliente.](/windows/win32/events/windows-events) 

Os eventos do Windows incluem várias fontes de eventos de segurança, incluindo eventos [](/windows/device-security/auditing/security-auditing-overview) SAM (Security Account Manager) ( aprimorados para[o Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), também consulte o tópico auditoria de segurança) e [Windows Defender eventos](troubleshoot-microsoft-defender-antivirus.md). 

Esses eventos podem ser agregados centralmente usando o coletor [de eventos do Windows](/windows/win32/wec/windows-event-collector). Frequentemente, os servidores SIEM têm conectores para eventos do Windows, permitindo correlacionar todos os eventos de segurança em seu servidor SIEM. 

Você também pode [monitorar eventos de malware usando a solução de Avaliação de Malware no Log Analytics.](/azure/log-analytics/log-analytics-malware)

Para monitorar ou determinar o status com PowerShell, WMI ou Microsoft Azure, consulte [a tabela (Opções](deploy-manage-report-microsoft-defender-antivirus.md#ref2)de implantação, gerenciamento e relatório) .

## <a name="related-articles"></a>Artigos relacionados

- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivírus no Windows Server 2016 e 2019](microsoft-defender-antivirus-on-windows-server.md)
- [Implantar o Microsoft Defender Antivírus](deploy-manage-report-microsoft-defender-antivirus.md)