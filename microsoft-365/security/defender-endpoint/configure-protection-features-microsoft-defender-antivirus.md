---
title: Habilitar e configurar recursos de proteção do Microsoft Defender Antivírus
description: Habilita a proteção baseada em comportamento, heurística e em tempo real no Microsoft Defender AV.
keywords: heurística, aprendizado de máquina, monitor de comportamento, proteção em tempo real, always-on, Microsoft Defender Antivírus, antimalware, segurança, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 9fc51682b659670a21c3c293ea8996beb228802a
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765066"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>Configurar a proteção comportamental, heurística e em tempo real

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

O Microsoft Defender Antivírus usa vários métodos para fornecer proteção contra ameaças:

- Proteção entregue na nuvem para detecção quase instantânea e bloqueio de ameaças novas e emergentes
- Verificação sempre em tempo real, usando monitoramento de comportamento de arquivo e processo e outras heurísticas (também conhecidas como "proteção em tempo real")
- Atualizações de proteção dedicadas com base em aprendizado de máquina, análise de grandes dimensões humana e automatizada e pesquisa de resistência de ameaças aprofundada

Você pode configurar como o Microsoft Defender Antivírus usa esses métodos com Política de Grupo, Gerenciamento de Configuração do System Center, cmdlets do PowerShell e Instrumentação de Gerenciamento do Windows (WMI).

Esta seção aborda a configuração para a verificação always-on, incluindo como detectar e bloquear aplicativos considerados não seguros, mas que podem não ser detectados como malware.

Consulte [Usar tecnologias do Microsoft Defender Antivírus](cloud-protection-microsoft-defender-antivirus.md) de próxima geração por meio da proteção entregue na nuvem para habilitar e configurar a proteção entregue na nuvem do Microsoft Defender Antivírus.

## <a name="in-this-section"></a>Nesta seção

 Tópico | Descrição
---|---
[Detectar e bloquear aplicativos potencialmente indesejados](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | Detectar e bloquear aplicativos que podem ser indesejados em sua rede, como adware, modificadores de navegador e barras de ferramentas e aplicativos antivírus desonestos ou falsos
[Habilitar e configurar recursos de proteção do Microsoft Defender Antivírus](configure-real-time-protection-microsoft-defender-antivirus.md) | Habilitar e configurar a proteção em tempo real, heurística e outros recursos de monitoramento always-on do Microsoft Defender Antivírus