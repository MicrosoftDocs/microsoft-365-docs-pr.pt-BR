---
title: Aplicar Microsoft Defender Antivírus atualizações após determinados eventos
description: Gerencie Microsoft Defender Antivírus aplica atualizações de inteligência de segurança após a inicialização ou recebimento de relatórios de detecção entregues na nuvem.
keywords: atualizações, proteção, atualizações de força, eventos, inicialização, verificar se há mais recentes, notificações
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 82aff7adedc9e490520851ad8c8e87fad60abf0a
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926074"
---
# <a name="manage-event-based-forced-updates"></a>Gerenciar atualizações aplicadas com base em evento

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivírus permite determinar se as atualizações devem (ou não) ocorrer após determinados eventos, como na inicialização ou depois de receber relatórios específicos do serviço de proteção entregue na nuvem.

## <a name="check-for-protection-updates-before-running-a-scan"></a>Verifique se há atualizações de proteção antes de executar uma verificação

Você pode usar Microsoft Endpoint Configuration Manager, Política de Grupo, cmdlets do PowerShell e WMI para forçar Microsoft Defender Antivírus verificar e baixar atualizações de proteção antes de executar uma verificação agendada.

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a>Use o Configuration Manager para verificar se há atualizações de proteção antes de executar uma verificação

1. Em seu console Microsoft Endpoint Manager, abra a política antimalware que  você deseja alterar (clique em Ativos e Conformidade no painel de navegação à esquerda e expanda a árvore para **Visão** geral  >  **Endpoint Protection**  >  **Políticas antimalware**)

2. Vá para a seção **Verificações** agendadas e **desem conjunto Verificar as** atualizações mais recentes de inteligência de segurança antes de executar uma verificação como **Sim**.

3. Clique em **OK**.

4. [Implantar a política atualizada como de costume](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a>Use a Política de Grupo para verificar se há atualizações de proteção antes de executar uma verificação

1. Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. Usando o **Editor de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**

3. Clique **em Políticas** e modelos **administrativos.**

4. Expanda a árvore para **Windows componentes**  >  **Microsoft Defender Antivírus**  >  **Scan**.

5. Clique duas **vezes em Verificar as definições mais** recentes de vírus e spyware antes de executar uma verificação agendada e de definir a opção como **Habilitado**.

6. Clique em **OK**.

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a>Use cmdlets do PowerShell para verificar se há atualizações de proteção antes de executar uma verificação

Use os seguintes cmdlets:

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

Para obter mais informações, confira [Usar cmdlets do PowerShell para configurar e executar o Microsoft Defender Antivírus](use-powershell-cmdlets-microsoft-defender-antivirus.md) e [cmdlets do Defender](/powershell/module/defender/index).

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a>Use Windows Instrução de Gerenciamento (WMI) para verificar se há atualizações de proteção antes de executar uma verificação

Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:

```WMI
CheckForSignaturesBeforeRunningScan
```

Para obter mais informações, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

## <a name="check-for-protection-updates-on-startup"></a>Verificar se há atualizações de proteção na inicialização

Você pode usar a Política de Grupo para forçar Microsoft Defender Antivírus verificar e baixar atualizações de proteção quando o computador for iniciado.

1. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. Usando o **Editor de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**

3. Clique **em Políticas** e modelos **administrativos.**

4. Expanda a árvore para **Windows componentes**  >  **Microsoft Defender Antivírus**  >  **Atualizações de Inteligência de Segurança.**

5. Clique duas **vezes em Verificar as definições mais** recentes de vírus e spyware na inicialização e de definir a opção como **Habilitado**. 

6. Clique em **OK**.

Você também pode usar a Política de Grupo, o PowerShell ou o WMI para configurar o Microsoft Defender Antivírus para verificar se há atualizações na inicialização, mesmo quando ela não está em execução.

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Usar a Política de Grupo para baixar atualizações quando Microsoft Defender Antivírus não estiver presente

1. Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. Usando o **Editor de Gerenciamento de Política de Grupo,** vá para **Configuração do computador**.

3. Clique **em Políticas** e modelos **administrativos.**

4. Expanda a árvore para **Windows componentes**  >  **Microsoft Defender Antivírus**  >  **Atualizações de Inteligência de Segurança.**

5. Clique duas vezes em **Iniciar atualização de inteligência de segurança na inicialização** e de definir a opção como **Habilitado**.

6. Clique em **OK**.

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Usar cmdlets do PowerShell para baixar atualizações quando Microsoft Defender Antivírus não estiver presente

Use os seguintes cmdlets:

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

Para obter mais informações, consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para gerenciar [cmdlets](/powershell/module/defender/index) Microsoft Defender Antivírus e Defender para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus.

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>Use Windows Instrução de Gerenciamento (WMI) para baixar atualizações quando Microsoft Defender Antivírus não estiver presente

Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

Para obter mais informações, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a>Permitir alterações ad hoc na proteção com base na proteção entregue na nuvem

O Microsoft Defender AV pode fazer alterações em sua proteção com base na proteção entregue na nuvem. Essas alterações podem ocorrer fora das atualizações de proteção normais ou agendadas.

Se você habilitar a proteção entregue na nuvem, o Microsoft Defender AV enviará arquivos suspeitos para a Windows Defender nuvem. Se o serviço de nuvem relata que o arquivo é mal-intencionado e o arquivo é detectado em uma atualização de proteção recente, você pode usar a Política de Grupo para configurar o Microsoft Defender AV para receber automaticamente essa atualização de proteção. Outras atualizações de proteção importantes também podem ser aplicadas.

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a>Usar a Política de Grupo para baixar automaticamente atualizações recentes com base na proteção entregue na nuvem

1. Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. Usando o **Editor de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**

3. Clique **em Políticas** e modelos **administrativos.**

4. Expanda a árvore para **Windows componentes**  >  **Microsoft Defender Antivírus**  >  **Atualizações de Inteligência de Segurança.**

5. Clique duas vezes **em Permitir atualizações de** inteligência de segurança em tempo real com base em relatórios para o Microsoft MAPS e de definir a opção **como Habilitado.** Clique em **OK**.

6. **Permitir notificações para desabilitar relatórios baseados** em definições para o Microsoft MAPS e definir a opção como **Habilitado**. Clique em **OK**.
    
> [!NOTE]
> **Permitir notificações para desabilitar relatórios baseados** em definições permite que o Microsoft MAPS desabilite essas definições conhecidas por causar relatórios falsos positivos. Você deve configurar seu computador para ingressar no Microsoft MAPS para que essa função funcione.

## <a name="see-also"></a>Confira também

- [Implantar Microsoft Defender Antivírus](deploy-manage-report-microsoft-defender-antivirus.md)
- [Gerenciar Microsoft Defender Antivírus e aplicar linhas de base](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Gerenciar quando as atualizações de proteção devem ser baixadas e aplicadas](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [Gerenciar atualizações para pontos de extremidade que estão des date](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Gerenciar atualizações para dispositivos móveis e máquinas virtuais (VMs)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)