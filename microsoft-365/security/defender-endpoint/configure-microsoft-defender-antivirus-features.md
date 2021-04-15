---
title: Configurar recursos do Microsoft Defender Antivírus
description: Você pode configurar recursos do Microsoft Defender Antivírus com o Intune, o Microsoft Endpoint Configuration Manager, a Política de Grupo e o PowerShell.
keywords: Microsoft Defender Antivírus, antimalware, segurança, defender, configurar, configuração, Config Manager, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, gerenciamento de dispositivo móvel, GP, política de grupo, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8503bb5bdd6337ec60390ef1d8e59f6f506fbce2
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765162"
---
# <a name="configure-microsoft-defender-antivirus-features"></a>Configurar recursos do Microsoft Defender Antivírus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Você pode configurar o Microsoft Defender Antivírus com várias ferramentas, incluindo:

- Microsoft Intune
- Gerenciador de Configuração do Microsoft Endpoint
- Política de Grupo
- Cmdlets do PowerShell
- Instrumentação de Gerenciamento do Windows (WMI)

As seguintes categorias amplas de recursos podem ser configuradas:

- Proteção entregue na nuvem
- Proteção sempre em tempo real, incluindo proteção comportamental, heurística e baseada em aprendizado de máquina
- Como os usuários finais interagem com o cliente em pontos de extremidade individuais

Os artigos a seguir descrevem como executar tarefas importantes ao configurar o Microsoft Defender Antivírus. Cada artigo inclui instruções para a ferramenta de configuração aplicável (ou ferramentas).

|Artigo  |Descrição  |
|---------|---------|
|[Usar a proteção do Microsoft Defender Antivírus fornecida na nuvem pela Microsoft](cloud-protection-microsoft-defender-antivirus.md)     | Use a proteção entregue na nuvem para detecção avançada, rápida e robusta de antivírus.        |
|[Configurar a proteção comportamental, heurística e em tempo real](configure-protection-features-microsoft-defender-antivirus.md)     |Habilita a proteção antivírus baseada em comportamento, heurística e em tempo real.         |
|[Configurar a interação do usuário final com o Microsoft Defender Antivírus](configure-end-user-interaction-microsoft-defender-antivirus.md) | Configure como os usuários finais em sua organização interagem com o Microsoft Defender Antivírus, quais notificações eles veem e se eles podem substituir as configurações. |

> [!TIP]
> Você também pode revisar os [tópicos De referência](configuration-management-reference-microsoft-defender-antivirus.md) para ferramentas de gerenciamento e configuração para uma visão geral de cada ferramenta e links para ajudar ainda mais.