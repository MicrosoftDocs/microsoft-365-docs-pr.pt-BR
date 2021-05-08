---
title: Configurar recursos do Microsoft Defender Antivírus
description: Você pode configurar Microsoft Defender Antivírus recursos com o Intune, Microsoft Endpoint Configuration Manager, Política de Grupo e PowerShell.
keywords: Microsoft Defender Antivírus, antimalware, segurança, defender, configurar, configuração, Gerenciador de Configurações, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, gerenciamento de dispositivo móvel, GP, política de grupo, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4408d5e788449c0d094008261f5e7db9bfe38758
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275103"
---
# <a name="configure-microsoft-defender-antivirus-features"></a>Configurar recursos do Microsoft Defender Antivírus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Você pode configurar Microsoft Defender Antivírus com várias ferramentas, incluindo:

- Microsoft Intune
- Gerenciador de Configuração do Microsoft Endpoint
- Política de Grupo
- Cmdlets do PowerShell
- Windows Instrumentação de Gerenciamento (WMI)

As seguintes categorias amplas de recursos podem ser configuradas:

- Proteção fornecida na nuvem
- Proteção sempre em tempo real, incluindo proteção comportamental, heurística e baseada em aprendizado de máquina
- Como os usuários finais interagem com o cliente em pontos de extremidade individuais

Os artigos a seguir descrevem como executar tarefas-chave ao configurar Microsoft Defender Antivírus. Cada artigo inclui instruções para a ferramenta de configuração aplicável (ou ferramentas).

|Artigo  |Descrição  |
|---------|---------|
|[Usar a proteção Microsoft Defender Antivírus microsoft](cloud-protection-microsoft-defender-antivirus.md)     | Use a proteção entregue na nuvem para detecção avançada, rápida e robusta de antivírus.        |
|[Configurar a proteção comportamental, heurística e em tempo real](configure-protection-features-microsoft-defender-antivirus.md)     |Habilita a proteção antivírus baseada em comportamento, heurística e em tempo real.         |
|[Configurar a interação do usuário final com Microsoft Defender Antivírus](configure-end-user-interaction-microsoft-defender-antivirus.md) | Configure como os usuários finais em sua organização interagem com Microsoft Defender Antivírus, quais notificações eles veem e se eles podem substituir as configurações. |

> [!TIP]
> Você também pode revisar os [tópicos De referência](configuration-management-reference-microsoft-defender-antivirus.md) para ferramentas de gerenciamento e configuração para uma visão geral de cada ferramenta e links para ajudar ainda mais.