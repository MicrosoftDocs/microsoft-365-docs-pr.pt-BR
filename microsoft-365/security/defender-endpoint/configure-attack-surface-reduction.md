---
title: Configurar os recursos de redução da superfície de ataque
description: Use Microsoft Intune, Microsoft Endpoint Configuration Manager, cmdlets do PowerShell e Política de Grupo para configurar a redução de superfície de ataque.
keywords: asr, redução de superfície de ataque, windows defender, microsoft defender, antivírus, av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 948b5dc201526bf54aae0e857cfd40dcc9fe1e19
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984443"
---
# <a name="configure-attack-surface-reduction-capabilities"></a>Configurar os recursos de redução da superfície de ataque

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).

O Defender para Ponto de Extremidade inclui vários recursos de redução de superfície de ataque. Para saber mais, confira [Visão geral dos recursos de redução de superfície de ataque.](overview-attack-surface-reduction.md) Para configurar a redução de superfície de ataque em seu ambiente, siga estas etapas:

1. [Habilitar o isolamento baseado em hardware para Microsoft Edge](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard).

2. Habilitar o controle do aplicativo.

   1. Revise as políticas básicas Windows. Consulte [Example Base Policies](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies).
   2. Consulte o guia [Windows Defender design do Controle de Aplicativos.](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide)
   3. Consulte [Deploying Windows Defender Application Control (WDAC).](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide)

3. [Habilitar acesso controlado a pastas](enable-controlled-folders.md).

4. [Ativar a proteção de rede](enable-network-protection.md).

5. [Habilitar a proteção de exploração](enable-exploit-protection.md).

6. [Configurar regras de redução de superfície de ataque](enable-attack-surface-reduction.md).

7. Configurar o firewall de rede.

   1. Obter uma visão geral do [Windows Defender Firewall com segurança avançada.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
   2. Use o [Windows Defender de design do Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) para decidir como você deseja projetar suas políticas de firewall.
   3. Use o [Windows Defender de implantação do Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) para configurar o firewall da sua organização com segurança avançada.

> [!TIP]
> Na maioria dos casos, ao configurar recursos de redução de superfície de ataque, você pode escolher entre vários métodos:

> - Microsoft Endpoint Manager (que agora inclui Microsoft Intune e Microsoft Endpoint Configuration Manager)
> - Política de Grupo
> - Cmdlets do PowerShell
