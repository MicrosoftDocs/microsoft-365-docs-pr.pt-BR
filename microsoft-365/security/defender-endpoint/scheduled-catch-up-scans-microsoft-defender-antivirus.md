---
title: Agendar verificações rápidas e completas regulares com o Microsoft Defender Antivírus
description: Configurar verificações recorrentes (agendadas), incluindo quando devem ser executados e se são executados como verificações completas ou rápidas
keywords: verificação rápida, verificação completa, rápida versus completa, verificação de agendamento, diariamente, semanal, hora, agendada, recorrente, regular
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/02/2020
ms.reviewer: pauhijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 66907fca7a117eeba7ca0b9bd95d59af24c31341
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689870"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>Configurar verificações rápidas ou completas agendadas do Microsoft Defender Antivírus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> Por padrão, o Microsoft Defender Antivírus verifica se há uma atualização 15 minutos antes da hora de qualquer verificação agendada. Você pode Gerenciar a agenda para quando as atualizações de proteção devem ser baixadas e [aplicadas](manage-protection-update-schedule-microsoft-defender-antivirus.md) para substituir esse padrão. 

Além da proteção sempre em tempo [](run-scan-microsoft-defender-antivirus.md) real e verificações sob demanda, você pode configurar verificações regulares agendadas. 

Você pode configurar o tipo de verificação, quando a verificação deve ocorrer e se [a](manage-protection-updates-microsoft-defender-antivirus.md) verificação deve ocorrer após uma atualização de proteção ou se o ponto de extremidade está sendo usado. Você também pode especificar quando verificações especiais para concluir a correção devem ocorrer.

Este artigo descreve como configurar verificações agendadas com Política de Grupo, cmdlets do PowerShell e WMI. Você também pode configurar verificações de agendamentos com [o Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) ou o Microsoft [Intune](/mem/intune/configuration/device-restrictions-windows-10).

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a>Para configurar as configurações da Política de Grupo descritas neste artigo

1.  Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

3.  No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**

4.  Clique **em Modelos Administrativos**.

5.  Expanda a árvore **para componentes do Windows > o Microsoft Defender Antivírus** e, em seguida, o **Local** especificado na tabela abaixo.

6. Clique duas vezes na **configuração de** política, conforme especificado na tabela abaixo, e de definir a opção para a configuração desejada. 

7. Clique **em OK** e repita para quaisquer outras configurações.

Consulte também [Os tópicos Gerenciar quando](manage-protection-update-schedule-microsoft-defender-antivirus.md) as atualizações de proteção devem ser baixadas e aplicadas e Impedir ou permitir que os usuários modifiquem [localmente](configure-local-policy-overrides-microsoft-defender-antivirus.md) os tópicos das configurações de política.

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a>Verificação rápida versus verificação completa e verificação personalizada

Ao configurar verificações agendadas, você pode configurar se a verificação deve ser completa ou rápida.

Verificações rápidas analisam todos os locais onde pode haver malware registrado para começar com o sistema, como chaves do Registro e pastas de inicialização conhecidas do Windows. 

Combinado com a funcionalidade de proteção sempre em tempo [real](configure-real-time-protection-microsoft-defender-antivirus.md) - que revisa os arquivos quando eles são abertos e fechados e sempre que um usuário navega para uma pasta - uma verificação rápida ajuda a fornecer uma cobertura forte tanto para malware que começa com o sistema quanto o malware no nível do kernel.  

Na maioria das instâncias, isso significa que uma verificação rápida é adequada para encontrar malware que não foi escolhido pela proteção em tempo real.

Uma verificação completa pode ser útil em pontos de extremidade que encontraram uma ameaça de malware para identificar se há componentes inativos que exigem uma limpeza mais completa. Nesta instância, talvez você queira usar uma verificação completa ao executar uma verificação sob [demanda.](run-scan-microsoft-defender-antivirus.md)

Uma verificação personalizada permite que você especifique os arquivos e pastas a examinar, como uma unidade USB. 

>[!NOTE]
>Por padrão, verificações rápidas são executados em dispositivos removíveis montados, como unidades USB.

## <a name="set-up-scheduled-scans"></a>Configurar verificações agendadas

As verificações agendadas serão realizadas no dia e hora especificados. Você pode usar a Política de Grupo, o PowerShell e o WMI para configurar verificações agendadas.

>[!NOTE]
>Se um computador estiver desconectado e em execução na bateria durante uma verificação completa agendada, a verificação agendada será interrompida com o evento 1002, que afirma que a verificação parou antes da conclusão. O Microsoft Defender Antivírus executará uma verificação completa na próxima hora agendada.

### <a name="use-group-policy-to-schedule-scans"></a>Usar a Política de Grupo para agendar verificações

|Local | Setting | Descrição | Configuração padrão (se não estiver configurada) |
|:---|:---|:---|:---|
|Examinar | Especificar o tipo de verificação a ser usado para uma verificação agendada | Verificação rápida |
|Examinar | Especificar o dia da semana para executar uma verificação agendada | Especifique o dia (ou nunca) para executar uma verificação. | Nunca |
|Examinar | Especificar a hora do dia para executar uma verificação agendada | Especifique o número de minutos após a meia-noite (por exemplo, insira **60** para 1 da manhã). | 2 da manhã. |
|Root | Randomize tempos de tarefa agendados |No Microsoft Defender Antivírus: randomize a hora de início da verificação para qualquer intervalo de 0 a 4 horas. <br>No FEP/SCEP: aleatoriamente para qualquer intervalo mais ou menos 30 minutos. Isso pode ser útil em implantações VM ou VDI. | Habilitado |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a>Usar cmdlets do PowerShell para agendar verificações

Use os seguintes cmdlets:

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/) do Microsoft Defender Antivírus e do Defender para obter mais informações sobre como usar o PowerShell com o Microsoft Defender Antivírus.

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>Usar a Instrução de Gerenciamento do Windows (WMI) para agendar verificações

Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

Confira o seguinte para obter mais informações e parâmetros permitidos:
- [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a>Iniciar verificações agendadas somente quando o ponto de extremidade não estiver em uso

Você pode definir a verificação agendada para ocorrer somente quando o ponto de extremidade estiver ligado, mas não estiver em uso com a Política de Grupo, o PowerShell ou o WMI.

> [!NOTE]
> Essas verificações não cumprirão a configuração de limitador de CPU e tirarão total proveito dos recursos disponíveis para concluir a verificação o mais rápido possível.

### <a name="use-group-policy-to-schedule-scans"></a>Usar a Política de Grupo para agendar verificações

|Local | Setting | Descrição | Configuração padrão (se não estiver configurada) |
|:---|:---|:---|:---|
|Examinar | Iniciar a verificação agendada somente quando o computador estiver em uso, mas não estiver em uso | As verificações agendadas não serão executados, a menos que o computador esteja, mas não esteja em uso | Habilitado |

### <a name="use-powershell-cmdlets"></a>Usar cmdlets do PowerShell

Use os seguintes cmdlets:

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/) do Microsoft Defender Antivírus e do Defender para obter mais informações sobre como usar o PowerShell com o Microsoft Defender Antivírus.

### <a name="use-windows-management-instruction-wmi"></a>Usar a Instrução de Gerenciamento do Windows (WMI)

Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:

```WMI
ScanOnlyIfIdleEnabled
```

Confira o seguinte para obter mais informações e parâmetros permitidos:
- [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a>Configurar quando verificações completas devem ser executados para concluir a correção

Algumas ameaças podem exigir uma verificação completa para concluir sua remoção e correção. Você pode agendar quando essas verificações devem ocorrer com a Política de Grupo, o PowerShell ou o WMI.

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a>Usar a Política de Grupo para agendar verificações necessárias para correção

| Local | Setting | Descrição | Configuração padrão (se não estiver configurada) |
|---|---|---|---|
|Correção | Especificar o dia da semana para executar uma verificação completa agendada para concluir a correção | Especifique o dia (ou nunca) para executar uma verificação. | Nunca |
|Correção | Especificar a hora do dia para executar uma verificação completa agendada para concluir a correção | Especifique o número de minutos após a meia-noite (por exemplo, **insira 60** para 1 da manhã) | 2 da manhã. |

### <a name="use-powershell-cmdlets"></a>Usar cmdlets do PowerShell

Use os seguintes cmdlets:

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/) do Microsoft Defender Antivírus e do Defender para obter mais informações sobre como usar o PowerShell com o Microsoft Defender Antivírus.

### <a name="use-windows-management-instruction-wmi"></a>Usar a Instrução de Gerenciamento do Windows (WMI)

Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

Confira o seguinte para obter mais informações e parâmetros permitidos:
- [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="set-up-daily-quick-scans"></a>Configurar verificações rápidas diárias

Você pode habilitar uma verificação rápida diária que pode ser executado além de outras verificações agendadas com a Política de Grupo, o PowerShell ou o WMI.


### <a name="use-group-policy-to-schedule-daily-scans"></a>Usar a Política de Grupo para agendar verificações diárias


|Local | Setting | Descrição | Configuração padrão (se não estiver configurada) |
|:---|:---|:---|:---|
|Examinar | Especificar o intervalo para executar verificações rápidas por dia | Especifique quantas horas devem ser completas antes da próxima verificação rápida. Por exemplo, para executar a cada duas horas, insira **2**, uma vez por dia, insira **24**. Insira **0** para nunca executar uma verificação rápida diária. | Nunca |
|Examinar | Especifique o tempo para uma verificação rápida diária | Especifique o número de minutos após a meia-noite (por exemplo, **insira 60** para 1 da manhã) | 2 da manhã. |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a>Usar cmdlets do PowerShell para agendar verificações diárias

Use os seguintes cmdlets:

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/) do Microsoft Defender Antivírus e do Defender para obter mais informações sobre como usar o PowerShell com o Microsoft Defender Antivírus.

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a>Usar a Instrução de Gerenciamento do Windows (WMI) para agendar verificações diárias

Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:

```WMI
ScanScheduleQuickScanTime
```

Confira o seguinte para obter mais informações e parâmetros permitidos:
- [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="enable-scans-after-protection-updates"></a>Habilitar verificações após atualizações de proteção

Você pode forçar uma verificação a ocorrer após cada atualização [de proteção](manage-protection-updates-microsoft-defender-antivirus.md) com a Política de Grupo.

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a>Usar a Política de Grupo para agendar verificações após atualizações de proteção

|Local | Setting | Descrição | Configuração padrão (se não estiver configurada)|
|:---|:---|:---|:---|
|Atualizações de assinatura | Ativar a verificação após a atualização de Inteligência de Segurança | Uma verificação ocorrerá imediatamente depois que uma nova atualização de proteção for baixada | Habilitado |

## <a name="see-also"></a>Confira também
- [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [Configurar e executar verificações do Microsoft Defender Antivírus sob demanda](run-scan-microsoft-defender-antivirus.md)
- [Configurar opções de verificação do Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Gerenciar atualizações do Microsoft Defender Antivírus e aplicar linhas de base](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Gerenciar quando as atualizações de proteção devem ser baixadas e aplicadas](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)