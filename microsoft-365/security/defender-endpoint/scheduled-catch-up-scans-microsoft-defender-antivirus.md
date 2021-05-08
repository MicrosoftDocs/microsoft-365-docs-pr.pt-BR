---
title: Agendar verificações rápidas e completas regulares com Microsoft Defender Antivírus
description: Configurar verificações recorrentes (agendadas), incluindo quando devem ser executados e se são executados como verificações completas ou rápidas
keywords: verificação rápida, verificação completa, rápida versus completa, verificação de agendamento, diariamente, semanal, hora, agendada, recorrente, regular
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/05/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 1748a33be2c27123eb0437784dcdb2cb7905616a
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274683"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>Configurar verificações rápidas ou completas do Microsoft Defender Antivírus agendadas

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> Por padrão, Microsoft Defender Antivírus verifica se há uma atualização 15 minutos antes da hora de quaisquer verificações agendadas. Você pode Gerenciar a agenda para quando as atualizações de proteção devem ser baixadas e [aplicadas](manage-protection-update-schedule-microsoft-defender-antivirus.md) para substituir esse padrão. 

Além da proteção sempre em tempo [](run-scan-microsoft-defender-antivirus.md) real e verificações sob demanda, você pode configurar verificações regulares agendadas. 

Você pode configurar o tipo de verificação, quando a verificação deve ocorrer e se [a](manage-protection-updates-microsoft-defender-antivirus.md) verificação deve ocorrer após uma atualização de proteção ou se o ponto de extremidade está sendo usado. Você também pode especificar quando verificações especiais para concluir a correção devem ocorrer.

Este artigo descreve como configurar verificações agendadas com Política de Grupo, cmdlets do PowerShell e WMI. Você também pode configurar verificações de agendamentos [com Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) ou [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a>Para configurar as configurações da Política de Grupo descritas neste artigo

1. Em sua máquina de gerenciamento de Política de Grupo, no Editor de Política de Grupo, acesse Configuração do computador Modelos administrativos Windows  >    >  **Componentes**  >  **Microsoft Defender Antivírus**  >  **Verificar**.

2. Clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.

3. Especifique as configurações do Objeto de Política de Grupo e selecione **OK**. 

4. Repita as etapas 1 a 4 para cada configuração que você deseja configurar.

5. Implante seu Objeto de Política de Grupo como você normalmente faz. Se você precisar de ajuda com objetos de política de grupo, consulte [Create a Group Policy Object](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).

Consulte também [Os tópicos Gerenciar quando](manage-protection-update-schedule-microsoft-defender-antivirus.md) as atualizações de proteção devem ser baixadas e aplicadas e Impedir ou permitir que os usuários modifiquem [localmente](configure-local-policy-overrides-microsoft-defender-antivirus.md) os tópicos das configurações de política.

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a>Verificação rápida versus verificação completa e verificação personalizada

Ao configurar verificações agendadas, você pode configurar se a verificação deve ser completa ou rápida.


|Verificação rápida  |Verificação completa  | Verificação personalizada |
|---------|---------|---------|
|Uma verificação rápida analisa todos os locais onde pode haver malware registrado para começar com o sistema, como chaves de registro e pastas de inicialização Windows conhecidas. <p>Na maioria dos casos, uma verificação rápida é suficiente e é recomendada para verificações agendadas. |Uma verificação completa é iniciada executando uma verificação rápida e, em seguida, continua com uma verificação de arquivo sequencial de todos os discos fixos montados e unidades removíveis/de rede (se a verificação completa estiver configurada para fazer isso). <p>Uma verificação completa pode levar algumas horas ou dias para ser concluída, dependendo da quantidade e do tipo de dados que precisam ser verificados.<p>Quando a verificação completa for concluída, a nova inteligência de segurança estará disponível e uma nova verificação será necessária para garantir que nenhuma outra ameaça seja detectada com a nova inteligência de segurança.   | Uma verificação personalizada é uma verificação rápida que é executado nos arquivos e pastas que você especificar. Por exemplo, você pode optar por examinar uma unidade USB ou uma pasta específica na unidade local do dispositivo. <p> | 

>[!NOTE]
>Por padrão, verificações rápidas são executados em dispositivos removíveis montados, como unidades USB.

### <a name="how-do-i-know-which-scan-type-to-choose"></a>Como saber qual tipo de verificação escolher?

Use a tabela a seguir para escolher um tipo de verificação.


|Cenário  |Tipo de verificação recomendado  |
|---------|---------|
|Você deseja configurar verificações regulares agendadas     | Verificação rápida <p>Uma verificação rápida verifica os processos, memória, perfis e determinados locais no dispositivo. Combinado com [a proteção sempre em tempo real,](configure-real-time-protection-microsoft-defender-antivirus.md)uma verificação rápida ajuda a fornecer uma cobertura forte para malware que começa com o sistema e malware no nível do kernel. A proteção em tempo real revisa arquivos quando são abertos e fechados e sempre que um usuário navega para uma pasta.         |
|Ameaças, como malware, são detectadas em um dispositivo     | Verificação completa <p>Uma verificação completa pode ajudar a identificar se há componentes inativos que exigem uma limpeza mais completa.         |
|Você deseja executar uma verificação [sob demanda](run-scan-microsoft-defender-antivirus.md)     | Verificação completa  <p>Uma verificação completa analisa todos os arquivos no disco do dispositivo, incluindo arquivos que são antigos, arquivados e não acessados diariamente.      |
| Você deseja garantir que um dispositivo portátil, como uma unidade USB, não contenha malware | Verificação personalizada <p>Uma verificação personalizada permite selecionar locais, pastas ou arquivos específicos e executa uma verificação rápida. |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a>O que mais preciso saber sobre verificações rápidas e completas?

- Arquivos mal-intencionados podem ser armazenados em locais que não estão incluídos em uma verificação rápida. No entanto, a proteção sempre em tempo real revisa todos os arquivos abertos e fechados e todos os arquivos que estão em pastas acessadas por um usuário. A combinação de proteção em tempo real e uma verificação rápida ajuda a fornecer uma proteção forte contra malware.

- A proteção ao acessar [com](cloud-protection-microsoft-defender-antivirus.md) a proteção entregue na nuvem ajuda a garantir que todos os arquivos acessados no sistema estão sendo verificados com os modelos de aprendizado de máquina de nuvem e inteligência de segurança mais recentes.

- Quando a proteção em tempo real detecta malware e a extensão dos arquivos afetados não é determinada inicialmente, Microsoft Defender Antivírus inicia uma verificação completa como parte do processo de correção.

- Uma verificação completa pode detectar arquivos mal-intencionados que não foram detectados por outras verificações, como uma verificação rápida. No entanto, uma verificação completa pode demorar um pouco e usar recursos valiosos do sistema para ser concluído.

- Se um dispositivo estiver offline por um longo período de tempo, uma verificação completa poderá levar mais tempo para ser concluída. 

## <a name="set-up-scheduled-scans"></a>Configurar verificações agendadas

Verificações agendadas são realizadas no dia e hora especificados. Você pode usar a Política de Grupo, o PowerShell e o WMI para configurar verificações agendadas.

> [!NOTE]
> Se um dispositivo for desconectado e estiver sendo executado na bateria durante uma verificação completa agendada, a verificação agendada será interrompida com o evento 1002, que afirma que a verificação parou antes da conclusão. Microsoft Defender Antivírus executará uma verificação completa na próxima hora agendada.

### <a name="use-group-policy-to-schedule-scans"></a>Usar a Política de Grupo para agendar verificações

|Location | Setting | Descrição | Configuração padrão (se não estiver configurada) |
|:---|:---|:---|:---|
|Examinar | Especificar o tipo de verificação a ser usado para uma verificação agendada | Verificação rápida |
|Examinar | Especificar o dia da semana para executar uma verificação agendada | Especifique o dia (ou nunca) para executar uma verificação. | Nunca |
|Examinar | Especificar a hora do dia para executar uma verificação agendada | Especifique o número de minutos após a meia-noite (por exemplo, insira **60** para 1 da manhã). | 2 da manhã. |
|Root | Randomize tempos de tarefa agendados |Em Microsoft Defender Antivírus, randomize o horário de início da verificação para qualquer intervalo de 0 a 4 horas. <p>Em [SCEP,](/mem/intune/protect/certificates-scep-configure)randomize verifica para qualquer intervalo mais ou menos 30 minutos. Isso pode ser útil em máquinas virtuais ou implantações VDI. | Habilitado |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a>Usar cmdlets do PowerShell para agendar verificações

Use os seguintes cmdlets:

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

Para obter mais informações, consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/) Microsoft Defender Antivírus e Defender para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus.

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>Use Windows Instrução de Gerenciamento (WMI) para agendar verificações

Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

Para obter mais informações e parâmetros permitidos, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a>Iniciar verificações agendadas somente quando o ponto de extremidade não estiver em uso

Você pode definir a verificação agendada para ocorrer somente quando o ponto de extremidade estiver ligado, mas não estiver em uso com a Política de Grupo, o PowerShell ou o WMI.

> [!NOTE]
> Essas verificações não cumprirão a configuração de limitador de CPU e tirarão total proveito dos recursos disponíveis para concluir a verificação o mais rápido possível.

### <a name="use-group-policy-to-schedule-scans"></a>Usar a Política de Grupo para agendar verificações

|Location | Setting | Descrição | Configuração padrão (se não estiver configurada) |
|:---|:---|:---|:---|
|Examinar | Iniciar a verificação agendada somente quando o computador estiver em uso, mas não estiver em uso | As verificações agendadas não serão executados, a menos que o computador esteja, mas não esteja em uso | Habilitado |

### <a name="use-powershell-cmdlets"></a>Usar cmdlets do PowerShell

Use os seguintes cmdlets:

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

Para obter mais informações, [consulte Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/)Microsoft Defender Antivírus e Defender.

### <a name="use-windows-management-instruction-wmi"></a>Usar Windows Instrução de Gerenciamento (WMI)

Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:

```WMI
ScanOnlyIfIdleEnabled
```

Para obter mais informações sobre APIs e parâmetros permitidos, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a>Configurar quando verificações completas devem ser executados para concluir a correção

Algumas ameaças podem exigir uma verificação completa para concluir sua remoção e correção. Você pode especificar quando essas verificações devem ocorrer com Política de Grupo, PowerShell ou WMI.

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a>Usar a Política de Grupo para agendar verificações necessárias para correção

| Location | Setting | Descrição | Configuração padrão (se não estiver configurada) |
|---|---|---|---|
|Correção | Especificar o dia da semana para executar uma verificação completa agendada para concluir a correção | Especifique o dia (ou nunca) para executar uma verificação. | Nunca |
|Correção | Especificar a hora do dia para executar uma verificação completa agendada para concluir a correção | Especifique o número de minutos após a meia-noite (por exemplo, **insira 60** para 1 da manhã) | 2 da manhã. |

### <a name="use-powershell-cmdlets"></a>Usar cmdlets do PowerShell

Use os seguintes cmdlets:

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/) Microsoft Defender Antivírus e Defender para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus.

### <a name="use-windows-management-instruction-wmi"></a>Usar Windows Instrução de Gerenciamento (WMI)

Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

Para obter mais informações e parâmetros permitidos, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).


## <a name="set-up-daily-quick-scans"></a>Configurar verificações rápidas diárias

Você pode habilitar uma verificação rápida diária que pode ser executado além de outras verificações agendadas com a Política de Grupo, o PowerShell ou o WMI.

### <a name="use-group-policy-to-schedule-daily-scans"></a>Usar a Política de Grupo para agendar verificações diárias

|Location | Setting | Descrição | Configuração padrão (se não estiver configurada) |
|:---|:---|:---|:---|
|Examinar | Especificar o intervalo para executar verificações rápidas por dia | Especifique quantas horas devem ser completas antes da próxima verificação rápida. Por exemplo, para executar a cada duas horas, insira **2**, uma vez por dia, insira **24**. Insira **0** para nunca executar uma verificação rápida diária. | Nunca |
|Examinar | Especifique o tempo para uma verificação rápida diária | Especifique o número de minutos após a meia-noite (por exemplo, **insira 60** para 1 da manhã) | 2 da manhã. |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a>Usar cmdlets do PowerShell para agendar verificações diárias

Use os seguintes cmdlets:

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

Para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus, consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/)Microsoft Defender Antivírus e Defender.

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a>Use Windows Instrução de Gerenciamento (WMI) para agendar verificações diárias

Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:

```WMI
ScanScheduleQuickScanTime
```

Para obter mais informações e parâmetros permitidos, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).


## <a name="enable-scans-after-protection-updates"></a>Habilitar verificações após atualizações de proteção

Você pode forçar uma verificação a ocorrer após cada atualização [de proteção](manage-protection-updates-microsoft-defender-antivirus.md) com a Política de Grupo.

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a>Usar a Política de Grupo para agendar verificações após atualizações de proteção

|Location | Setting | Descrição | Configuração padrão (se não estiver configurada)|
|:---|:---|:---|:---|
|Atualizações de assinatura | Ativar a verificação após a atualização de Inteligência de Segurança | Uma verificação ocorrerá imediatamente depois que uma nova atualização de proteção for baixada | Habilitado |

## <a name="see-also"></a>Confira também

- [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [Configurar e executar verificações do Microsoft Defender Antivírus sob demanda](run-scan-microsoft-defender-antivirus.md)
- [Configurar opções de verificação do Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Gerenciar Microsoft Defender Antivírus e aplicar linhas de base](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Gerenciar quando as atualizações de proteção devem ser baixadas e aplicadas](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)