---
title: Bloqueio comportamental do cliente
description: O bloqueio comportamental do cliente faz parte dos recursos de bloqueio comportamental e de contenção no Microsoft Defender para Ponto de Extremidade
keywords: bloqueio comportamental, proteção rápida, comportamento do cliente, Microsoft Defender para Ponto de Extremidade
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 4e416aa9484f251280649035247a59dcc82ce750
ms.sourcegitcommit: bce733c1152dfbca782e716579074261e3c2ef65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52795953"
---
# <a name="client-behavioral-blocking"></a>Bloqueio comportamental do cliente

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>Visão Geral

O bloqueio comportamental do cliente é um componente dos recursos de [bloqueio comportamental e de contenção](behavioral-blocking-containment.md) no Defender para Ponto de Extremidade. À medida que comportamentos suspeitos são detectados em dispositivos (também chamados de clientes ou pontos de extremidade), artefatos (como arquivos ou aplicativos) são bloqueados, verificados e remediados automaticamente. 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Proteção de nuvem e cliente":::

A proteção antivírus funciona melhor quando emparelhada com a proteção de nuvem.

## <a name="how-client-behavioral-blocking-works"></a>Como funciona o bloqueio comportamental do cliente

[Microsoft Defender Antivírus](microsoft-defender-antivirus-in-windows-10.md) pode detectar comportamento suspeito, código mal-intencionado, ataques sem arquivo e na memória e muito mais em um dispositivo. Quando comportamentos suspeitos são detectados, Microsoft Defender Antivírus monitora e envia esses comportamentos suspeitos e suas árvores de processo para o serviço de proteção na nuvem. O aprendizado de máquina diferencia entre aplicativos mal-intencionados e bons comportamentos em milissegundos e classifica cada artefato. Em tempo quase real, assim que um artefato é considerado mal-intencionado, ele é bloqueado no dispositivo. 

Sempre que um comportamento suspeito é detectado, um [alerta](alerts-queue.md) é gerado e fica visível no Central de Segurança do Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

O bloqueio comportamental do cliente é eficaz porque não só ajuda a impedir que um ataque seja iniciado, como também pode ajudar a parar um ataque que começou a ser executado. E, com [o bloqueio de loop](feedback-loop-blocking.md) de feedback (outra funcionalidade de bloqueio comportamental e contenção), os ataques são impedidos em outros dispositivos em sua organização.

## <a name="behavior-based-detections"></a>Detecções baseadas em comportamento

As detecções baseadas em comportamento são nomeadas de acordo com o [MITRE ATT&CK Matrix para Enterprise](https://attack.mitre.org/matrices/enterprise). A convenção de nomeniste ajuda a identificar o estágio de ataque em que o comportamento mal-intencionado foi observado:


|Tática |   Nome da ameaça de detecção |
|----|----|
|Acesso Inicial | `Behavior:Win32/InitialAccess.*!ml` |
|Execução  | `Behavior:Win32/Execution.*!ml` |
|Persistência    | `Behavior:Win32/Persistence.*!ml` |
|Escalonamento de privilégios   | `Behavior:Win32/PrivilegeEscalation.*!ml` |
|Evasão de Defesa    | `Behavior:Win32/DefenseEvasion.*!ml` |
|Acesso de Credenciais  | `Behavior:Win32/CredentialAccess.*!ml` |
|Descoberta  | `Behavior:Win32/Discovery.*!ml` |
|Movimento Lateral | `Behavior:Win32/LateralMovement.*!ml` |
|Coleção |   `Behavior:Win32/Collection.*!ml` |
|Comando e Controle | `Behavior:Win32/CommandAndControl.*!ml` |
|Exfiltração   | `Behavior:Win32/Exfiltration.*!ml` |
|Impacto | `Behavior:Win32/Impact.*!ml` |
|Não categorizado  | `Behavior:Win32/Generic.*!ml` |

> [!TIP]
> Para saber mais sobre ameaças específicas, consulte **[atividade de ameaça global recente.](https://www.microsoft.com/wdsi/threats)**


## <a name="configuring-client-behavioral-blocking"></a>Configurando o bloqueio comportamental do cliente

Se sua organização estiver usando o Defender para Ponto de Extremidade, o bloqueio comportamental do cliente será habilitado por padrão. No entanto, para se beneficiar de [](behavioral-blocking-containment.md)todos os recursos do Defender para Ponto de Extremidade, incluindo bloqueio comportamental e contenção, certifique-se de que os seguintes recursos e recursos do Defender para Ponto de Extremidade estão habilitados e configurados:

- [Linha de base do Defender para Pontos de Extremidade](configure-machines-security-baseline.md)

- [Dispositivos a bordo do Defender para Ponto de Extremidade](onboard-configure.md)

- [EDR em modo de bloco](edr-in-block-mode.md)

- [Redução de superfície de ataque](attack-surface-reduction.md)

- [Proteção de última geração](configure-microsoft-defender-antivirus-features.md) (antivírus, antimalware e outros recursos de proteção contra ameaças)

