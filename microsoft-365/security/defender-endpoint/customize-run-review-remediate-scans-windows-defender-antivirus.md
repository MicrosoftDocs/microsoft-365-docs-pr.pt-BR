---
title: Executar e personalizar verificações agendadas e sob demanda
description: Personalizar e iniciar verificações do Microsoft Defender Antivírus em pontos de extremidade em toda a sua rede.
keywords: scan, schedule, customize, exclusions, exclude files, remediation, scan results, quarantine, remove threat, quick scan, full scan, Microsoft Defender Antivírus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f3e0cc7ffccf02e24b9746d539a44d3a72810ead
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765666"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans--remediation"></a>Personalizar, iniciar e revisar os resultados das verificações do Microsoft Defender Antivírus & correção

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Você pode usar a Política de Grupo, o PowerShell e a Instrumentação de Gerenciamento do Windows (WMI) para configurar verificações do Microsoft Defender Antivírus. 

## <a name="in-this-section"></a>Nesta seção

| Artigo | Descrição |
|:---|:---|
|[Configurar e validar exclusões de arquivo, pasta e processo aberto em verificações do Microsoft Defender Antivírus](configure-exclusions-microsoft-defender-antivirus.md) | Você pode excluir arquivos (incluindo arquivos modificados por processos especificados) e pastas de verificações sob demanda, verificações agendadas e monitoramento e verificação de proteção em tempo real sempre em tempo real |
|[Configurar opções de verificação do Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md) | Você pode configurar o Microsoft Defender Antivírus para incluir determinados tipos de arquivos de armazenamento de email, pontos de back-up ou reparse e arquivos arquivados (como arquivos .zip) em verificações. Você também pode habilitar a verificação de arquivos de rede |
|[Configurar correção para verificações](configure-remediation-microsoft-defender-antivirus.md) | Configure o que o Microsoft Defender Antivírus deve fazer quando detectar uma ameaça e por quanto tempo os arquivos em quarentena devem ser mantidos na pasta de quarentena |
|[Configurar verificações agendadas](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | Configurar verificações recorrentes (agendadas), incluindo quando devem ser executados e se são executados como verificações completas ou rápidas |
|[Configurar e executar verificações](run-scan-microsoft-defender-antivirus.md) | Executar e configurar verificações sob demanda usando o PowerShell, a Instrumentação de Gerenciamento do Windows ou individualmente nos pontos de extremidade com o aplicativo segurança do Windows |
|[Revisar resultados da verificação](review-scan-results-microsoft-defender-antivirus.md) | Revise os resultados das verificações usando o Microsoft Endpoint Configuration Manager, o Microsoft Intune ou o aplicativo de Segurança do Windows |