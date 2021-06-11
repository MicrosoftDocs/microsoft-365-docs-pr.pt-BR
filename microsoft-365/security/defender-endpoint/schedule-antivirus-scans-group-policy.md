---
title: Agendar verificações antivírus usando a Política de Grupo
description: Usar a Política de Grupo para configurar verificações antivírus
keywords: verificação rápida, verificação completa, agendamento, política de grupo, antivírus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 6f6018ec8b514234ab4f98e3d5416b472ff88739
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879648"
---
# <a name="schedule-antivirus-scans-using-group-policy"></a>Agendar verificações antivírus usando a Política de Grupo

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Este artigo descreve como configurar verificações agendadas usando a Política de Grupo. Para saber mais sobre o agendamento de verificações e sobre tipos de verificação, consulte [Configure scheduled quick or full Microsoft Defender Antivírus scans](schedule-antivirus-scans.md). 

## <a name="configure-antivirus-scans-using-group-policy"></a>Configurar verificações antivírus usando a Política de Grupo

1. Em sua máquina de gerenciamento de Política de Grupo, no Editor de Política de Grupo, acesse Configuração do computador Modelos administrativos Windows  >    >  **Componentes**  >  **Microsoft Defender Antivírus**  >  **Verificar**.

2. Clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.

3. Especifique as configurações do Objeto de Política de Grupo e selecione **OK**. 

4. Repita as etapas 1 a 4 para cada configuração que você deseja configurar.

5. Implante seu Objeto de Política de Grupo como você normalmente faz. Se você precisar de ajuda com objetos de política de grupo, consulte [Create a Group Policy Object](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).

> [!TIP]
> Consulte Os [tópicos Gerenciar quando](manage-protection-update-schedule-microsoft-defender-antivirus.md) as atualizações de proteção devem ser baixadas e aplicadas e Impedir ou permitir que os usuários modifiquem [localmente](configure-local-policy-overrides-microsoft-defender-antivirus.md) os tópicos das configurações de política.

## <a name="group-policy-settings-for-scheduling-scans"></a>Configurações da Política de Grupo para agendamento de verificações

| Local | Setting | Descrição | Configuração padrão (se não estiver configurada) |
|:---|:---|:---|:---|
| Examinar | Especificar o tipo de verificação a ser usado para uma verificação agendada | Verificação rápida |
| Examinar | Especificar o dia da semana para executar uma verificação agendada | Especifique o dia (ou nunca) para executar uma verificação. | Nunca |
| Examinar | Especificar a hora do dia para executar uma verificação agendada | Especifique o número de minutos após a meia-noite (por exemplo, insira **60** para 1 da manhã). | 2 da manhã. |
| Root | Randomize tempos de tarefa agendados |Em Microsoft Defender Antivírus, randomize o horário de início da verificação para qualquer intervalo de 0 a 4 horas. <p>Em [SCEP,](/mem/intune/protect/certificates-scep-configure)randomize verifica para qualquer intervalo mais ou menos 30 minutos. Isso pode ser útil em máquinas virtuais ou implantações VDI. | Habilitado |

## <a name="group-policy-settings-for-scheduling-scans-for-when-an-endpoint-is-not-in-use"></a>Configurações da Política de Grupo para agendamento de verificações para quando um ponto de extremidade não está em uso

| Local | Setting | Descrição | Configuração padrão (se não estiver configurada) |
|:---|:---|:---|:---|
| Examinar | Iniciar a verificação agendada somente quando o computador estiver em uso, mas não estiver em uso | As verificações agendadas não serão executados, a menos que o computador esteja, mas não esteja em uso | Habilitado |

> [!NOTE]
> Quando você agenda verifica os horários em que os pontos de extremidade não estão em uso, as verificações não honram a configuração de interrupção da CPU e aproveitam totalmente os recursos disponíveis para concluir a verificação o mais rápido possível.

## <a name="group-policy-settings-for-scheduling-remediation-required-scans"></a>Configurações da Política de Grupo para agendar verificações necessárias para correção

| Local | Setting | Descrição | Configuração padrão (se não estiver configurada) |
|---|---|---|---|
| Correção | Especificar o dia da semana para executar uma verificação completa agendada para concluir a correção | Especifique o dia (ou nunca) para executar uma verificação. | Nunca |
| Correção | Especificar a hora do dia para executar uma verificação completa agendada para concluir a correção | Especifique o número de minutos após a meia-noite (por exemplo, **insira 60** para 1 da manhã) | 2 da manhã. |

## <a name="group-policy-settings-for-scheduling-daily-scans"></a>Configurações da Política de Grupo para agendamento de verificações diárias

| Local | Setting | Descrição | Configuração padrão (se não estiver configurada) |
|:---|:---|:---|:---|
| Examinar | Especificar o intervalo para executar verificações rápidas por dia | Especifique quantas horas devem ser completas antes da próxima verificação rápida. Por exemplo, para executar a cada duas horas, insira **2**, uma vez por dia, insira **24**. Insira **0** para nunca executar uma verificação rápida diária. | Nunca |
| Examinar | Especifique o tempo para uma verificação rápida diária | Especifique o número de minutos após a meia-noite (por exemplo, **insira 60** para 1 da manhã) | 2 da manhã. |

## <a name="group-policy-settings-for-scheduling-scans-after-protection-updates"></a>Configurações da Política de Grupo para agendamento de verificações após atualizações de proteção

| Local | Setting | Descrição | Configuração padrão (se não estiver configurada)|
|:---|:---|:---|:---|
| Atualizações de assinatura | Ativar a verificação após a atualização de Inteligência de Segurança | Uma verificação ocorrerá imediatamente depois que uma nova atualização de proteção for baixada | Habilitado |

