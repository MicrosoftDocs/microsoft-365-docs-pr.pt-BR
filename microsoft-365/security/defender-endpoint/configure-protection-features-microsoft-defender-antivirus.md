---
title: Habilitar e configurar Microsoft Defender Antivírus recursos de proteção
description: Habilita a proteção baseada em comportamento, heurística e em tempo real no Microsoft Defender AV.
keywords: heurística, aprendizado de máquina, monitor de comportamento, proteção em tempo real, always-on, Microsoft Defender Antivírus, antimalware, segurança, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: d8ce2ded8fd3270bcb095022c714f07d8030e1f7
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925550"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>Configurar a proteção comportamental, heurística e em tempo real


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivírus usa vários métodos para fornecer proteção contra ameaças:

- Proteção entregue na nuvem para detecção quase instantânea e bloqueio de ameaças novas e emergentes
- Verificação sempre em tempo real, usando monitoramento de comportamento de arquivo e processo e outras heurísticas (também conhecidas como "proteção em tempo real")
- Atualizações de proteção dedicadas com base em aprendizado de máquina, análise de grandes dimensões humana e automatizada e pesquisa de resistência de ameaças aprofundada

Você pode configurar como Microsoft Defender Antivírus esses métodos com a Política de Grupo, System Center Configuration Manage, cmdlets do PowerShell e Windows Instrumentação de Gerenciamento (WMI).

Esta seção aborda a configuração para a verificação always-on, incluindo como detectar e bloquear aplicativos considerados não seguros, mas que podem não ser detectados como malware.

Consulte [Usar tecnologias de Microsoft Defender Antivírus](cloud-protection-microsoft-defender-antivirus.md) de próxima geração por meio da proteção entregue na nuvem para saber como habilitar e configurar Microsoft Defender Antivírus proteção entregue na nuvem.

## <a name="in-this-section"></a>Nesta seção

 Tópico | Descrição
---|---
[Detectar e bloquear aplicativos potencialmente indesejados](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | Detectar e bloquear aplicativos que podem ser indesejados em sua rede, como adware, modificadores de navegador e barras de ferramentas e aplicativos antivírus desonestos ou falsos
[Habilitar e configurar recursos Microsoft Defender Antivírus proteção](configure-real-time-protection-microsoft-defender-antivirus.md) | Habilitar e configurar a proteção em tempo real, a heurística e outros recursos de monitoramento Microsoft Defender Antivírus always-on
