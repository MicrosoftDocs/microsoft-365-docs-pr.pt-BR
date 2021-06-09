---
title: Monitorar e relatar sobre Microsoft Defender Antivírus proteção
description: Use o Configuration Manager ou as ferramentas de gerenciamento de eventos e informações de segurança (SIEM) para consumir relatórios e monitorar o Microsoft Defender AV com o PowerShell e o WMI.
keywords: siem, monitor, report, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 5780daaa65a4d83376dd7977e03e88e2d828befc
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269575"
---
# <a name="report-on-microsoft-defender-antivirus"></a>Relatório sobre o Microsoft Defender Antivírus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivírus é integrado ao Windows 10, Windows Server 2019 e Windows Server 2016. Microsoft Defender Antivírus é da sua proteção de última geração no Microsoft Defender para Ponto de Extremidade. A proteção de última geração ajuda a proteger seus dispositivos contra ameaças de software, como vírus, malware e spyware em email, aplicativos, nuvem e Web.

Com Microsoft Defender Antivírus, você tem várias opções para revisar o status e os alertas de proteção. Você pode usar Microsoft Endpoint Manager para [monitorar Microsoft Defender Antivírus](/configmgr/protect/deploy-use/monitor-endpoint-protection) ou [criar alertas de email.](/configmgr/protect/deploy-use/endpoint-configure-alerts) Ou você pode monitorar a proteção usando [Microsoft Intune](/intune/introduction-intune).  

O Microsoft Operations Management Suite tem um complemento de [Conformidade](/windows/deployment/update/update-compliance-get-started) de Atualização que relata os principais problemas Microsoft Defender Antivírus, incluindo atualizações de proteção e configurações de proteção em tempo real.

Se você tiver um servidor siem (gerenciamento de eventos) e informações de segurança de terceiros, você também poderá consumir Windows Defender [eventos de cliente.](/windows/win32/events/windows-events) 

Windows eventos incluem várias fontes de eventos de segurança, incluindo eventos SAM (Security [](/windows/device-security/auditing/security-auditing-overview) Account Manager)[(](/windows/whats-new/whats-new-windows-10-version-1507-and-1511)aprimorados para Windows 10 , também consulte o tópico auditoria de segurança) e Windows Defender [eventos](troubleshoot-microsoft-defender-antivirus.md). 

Esses eventos podem ser agregados centralmente usando o [coletor Windows evento](/windows/win32/wec/windows-event-collector). Frequentemente, os servidores SIEM têm conectores para eventos Windows, permitindo correlacionar todos os eventos de segurança em seu servidor SIEM. 

Você também pode [monitorar eventos de malware usando a solução de Avaliação de Malware no Log Analytics.](/azure/log-analytics/log-analytics-malware)

Para monitorar ou determinar o status com o PowerShell, WMI ou Microsoft Azure, consulte [a tabela (Opções](deploy-manage-report-microsoft-defender-antivirus.md#ref2)de implantação, gerenciamento e relatório) .

## <a name="related-articles"></a>Artigos relacionados

- [Microsoft Defender Antivirus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivírus no Windows Server 2016 e 2019](microsoft-defender-antivirus-on-windows-server.md)
- [Implantar Microsoft Defender Antivírus](deploy-manage-report-microsoft-defender-antivirus.md)