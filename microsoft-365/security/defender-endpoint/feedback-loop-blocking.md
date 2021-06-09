---
title: Bloqueio do loop de comentários
description: O bloqueio de loop de feedback, também chamado de proteção rápida, faz parte dos recursos de bloqueio comportamental e de contenção no Microsoft Defender para Ponto de Extremidade
keywords: bloqueio comportamental, proteção rápida, bloqueio de comentários, Microsoft Defender para Ponto de Extremidade
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection: ''
ms.technology: mde
ms.openlocfilehash: 7319ff5a89a20529eed7d36aa0d0b1522013abd4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842453"
---
# <a name="feedback-loop-blocking"></a>Bloqueio do loop de comentários

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a>Visão Geral

O bloqueio de loop de feedback, também conhecido [](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) como proteção rápida, é um componente dos recursos de bloqueio e contenção comportamental no Microsoft Defender para Ponto de [Extremidade.](/windows/security/threat-protection/) Com o bloqueio de loop de feedback, os dispositivos em toda a sua organização são mais protegidos contra ataques. 

## <a name="how-feedback-loop-blocking-works"></a>Como funciona o bloqueio de loop de feedback

Quando um comportamento ou arquivo suspeito é detectado, como por Microsoft Defender Antivírus [,](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)as informações sobre esse artefato são enviadas a vários classificadores. O mecanismo de loop de proteção rápida inspeciona e correlaciona as informações com outros sinais para chegar a uma decisão sobre se deve bloquear um arquivo. A verificação e a classificação de artefatos ocorrem rapidamente. Isso resulta no bloqueio rápido do malware confirmado e gera proteção em todo o ecossistema. 

Com a proteção rápida no local, um ataque pode ser interrompido em um dispositivo, em outros dispositivos na organização e em dispositivos em outras organizações, como uma tentativa de ataque para ampliar sua posição.


## <a name="configuring-feedback-loop-blocking"></a>Configurando o bloqueio de loop de feedback

Se sua organização estiver usando o Defender para Ponto de Extremidade, o bloqueio de loop de feedback será habilitado por padrão. No entanto, a proteção rápida ocorre por meio de uma combinação de recursos do Defender para Ponto de Extremidade, recursos de proteção de aprendizado de máquina e compartilhamento de sinal nos serviços de segurança da Microsoft. Certifique-se de que os seguintes recursos e recursos do Defender para Ponto de Extremidade estão habilitados e configurados:

- [Linha de base do Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [Dispositivos a bordo do Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/onboard-configure)

- [EDR em modo de bloco](/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [Redução de superfície de ataque](/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- [Proteção de última geração](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivírus)

## <a name="related-articles"></a>Artigos relacionados

- [Bloqueio e contenção comportamental](behavioral-blocking-containment.md)

- [(Blog) Bloqueio comportamental e contenção: transformar a ótica em proteção](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [Microsoft Defender útil para recursos de ponto de extremidade](/microsoft-365/security/defender-endpoint/helpful-resources)
