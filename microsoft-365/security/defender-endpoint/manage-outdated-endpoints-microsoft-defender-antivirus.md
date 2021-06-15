---
title: Aplicar atualizações de proteção do Microsoft Defender AV a pontos de extremidade des date
description: Defina quando e como as atualizações devem ser aplicadas para pontos de extremidade que não foram atualizados há algum tempo.
keywords: atualizações, proteção, desatualizados, desatualizados, antigos, catch-up
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
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b141c9b745e560b3c2236a9d073a7b2f3500623c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926038"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a>Gerenciar atualizações do Microsoft Defender Antivírus e verifica se há pontos de extremidade que estão desatualizados

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivírus permite definir por quanto tempo um ponto de extremidade pode evitar uma atualização ou quantas verificações ele pode falhar antes de ser necessário atualizar e verificar a si mesmo. Isso é especialmente útil em ambientes onde os dispositivos não estão frequentemente conectados a uma rede corporativa ou externa ou dispositivos que não são usados diariamente.

Por exemplo, um funcionário que usa um computador específico está em pausa por três dias e não faz logoff no computador durante esse tempo.

Quando o usuário retorna ao trabalho e faz logo em seu computador, o Microsoft Defender Antivírus verificará imediatamente e baixará as atualizações de proteção mais recentes e executará uma verificação.

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a>Configurar atualizações de proteção de catch-up para pontos de extremidade que não são atualizados há algum tempo

Se Microsoft Defender Antivírus as atualizações de proteção não foram baixadas por um período especificado, você pode defini-la para verificar e baixar automaticamente a atualização mais recente no próximo logoff. Isso será útil se você [tiver desabilitado globalmente](manage-event-based-updates-microsoft-defender-antivirus.md)os downloads de atualização automática na inicialização .

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a>Usar o Configuration Manager para configurar atualizações de proteção de atualização

1.  Em seu console Microsoft Endpoint Manager, abra a política antimalware que  você deseja alterar (clique em Ativos e Conformidade no painel de navegação à esquerda e expanda a árvore para **Visão** geral  >  **Endpoint Protection**  >  **Políticas antimalware**)

2.  Vá para a seção **Atualizações de Inteligência de** Segurança e configure as seguintes configurações:

    1. Definir Forçar uma atualização de inteligência de segurança se o computador cliente estiver offline para mais de duas atualizações **agendadas consecutivas** como **Sim**.
    2. Para o Gerenciador de Configurações if é usado como uma fonte para atualizações de inteligência de  **segurança...**, especifique as horas antes das quais as atualizações de proteção entregues pelo Configuration Manager devem ser consideradas des date. Isso fará com que o próximo local de atualização seja usado, com base na ordem de origem [de fallback definida.](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)

3. Clique em **OK**.

4.  [Implantar a política atualizada como de costume](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a>Usar a Política de Grupo para habilitar e configurar o recurso de atualização de atualização de catch-up

1. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**

3. Clique **em Políticas** e modelos **administrativos.**

4. Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus > Atualizações de Assinatura.**

5. Clique duas vezes na **configuração Definir** o número de dias após os quais uma atualização de inteligência de segurança de atualização é necessária e defina a opção **como Habilitado**. Insira o número de dias após os quais você deseja que o Microsoft Defender AV verifique e baixe a atualização de proteção mais recente.

6. Clique em **OK**.

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a>Usar cmdlets do PowerShell para configurar atualizações de proteção de atualização

Use os seguintes cmdlets:

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/) Microsoft Defender Antivírus e Defender para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus.

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a>Use Windows Instrução de Gerenciamento (WMI) para configurar atualizações de proteção de atualização

Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:

```WMI
SignatureUpdateCatchupInterval
```

Confira o seguinte para obter mais informações e parâmetros permitidos:
- [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a>Definir o número de dias antes que a proteção seja relatada como des date

Você também pode especificar o número de dias após os quais Microsoft Defender Antivírus proteção é considerada antiga ou desa data. Após o número especificado de dias, o cliente se reportará como desa datado e mostrará um erro para o usuário do computador. Também pode fazer com que Microsoft Defender Antivírus tente baixar uma atualização de outras fontes (com base na ordem de origem de [fallback](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)definida ), como ao usar o MMPC como uma fonte secundária após definir o WSUS ou o Microsoft Update como a primeira fonte.

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a>Use a Política de Grupo para especificar o número de dias antes que a proteção seja considerada desa atual

1.  Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

3.  No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**

4.  Clique **em Políticas** e modelos **administrativos.**

5.  Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus > Atualizações** de Assinatura e configure as seguintes configurações:

    1.  Clique duas vezes em Definir o número de dias antes que as definições de spyware sejam **consideradas** desa data e defina a opção **como Habilitado.** Insira o número de dias após os quais você deseja que o Microsoft Defender AV considere o spyware Security intelligence desagregado.

    2. Clique em **OK**.

    3.  Clique duas vezes em Definir o número de dias antes que as definições de vírus sejam **consideradas** desa data e defina a opção **como Habilitado**. Insira o número de dias após os quais você deseja que o Microsoft Defender AV considere a inteligência de segurança de vírus desagregada.

    4. Clique em **OK**.


## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a>Configurar verificações de catch-up para pontos de extremidade que não foram verificados por um tempo

Você pode definir o número de verificações agendadas consecutivas que podem ser perdidas antes Microsoft Defender Antivírus forçar uma verificação.

O processo para habilitação desse recurso é:

1. Configurar pelo menos uma verificação agendada (consulte o [tópico Agendar verificações).](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
2. Habilita o recurso de verificação de captura.
3. Defina o número de verificações que podem ser ignoradas antes que ocorra uma verificação de captura.

Esse recurso pode ser habilitado para verificações completas e rápidas.

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a>Usar a Política de Grupo para habilitar e configurar o recurso de verificação de captura

1.  Verifique se você definiu pelo menos uma verificação agendada.

2.  Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

3.  No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**

4.  Clique **em Políticas** e modelos **administrativos.**

5.  Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus > Verificar** e configurar as seguintes configurações:

    1.  Se você tiver definido as verificações  rápidas agendadas, clique duas vezes na configuração Ativar a verificação rápida de captura e de definir a opção **como Habilitado**. 
    2. Se você tiver definido as verificações  completas agendadas, clique duas vezes na configuração Ativar a verificação completa de captura e de definir a opção **como Habilitado**. Clique em **OK**.
    3. Clique duas vezes na **configuração Definir** o número de dias após os quais uma verificação de captura é forçada e defina a opção **como Habilitado**. 
    4. Insira o número de verificações que podem ser perdidas antes que uma verificação seja automaticamente executado quando o próximo usuário faz logor no computador. O tipo de verificação que é executado é determinado pelo tipo Especificar o tipo de verificação a ser usado para uma verificação **agendada** (consulte o tópico [Agendar verificações).](scheduled-catch-up-scans-microsoft-defender-antivirus.md) Clique em **OK**.

> [!NOTE]
> O título de configuração da Política de Grupo refere-se ao número de dias. A configuração, no entanto, é aplicada ao número de verificações (não dias) antes que a verificação de captura seja executado.

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a>Usar cmdlets do PowerShell para configurar verificações de captura

Use os seguintes cmdlets:

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

Consulte [Usar cmdlets do PowerShell para gerenciar cmdlets Microsoft Defender Antivírus](use-powershell-cmdlets-microsoft-defender-antivirus.md) e [Defender](/powershell/module/defender/) para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus.

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a>Use Windows Instrução de Gerenciamento (WMI) para configurar verificações de captura

Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

Confira o seguinte para obter mais informações e parâmetros permitidos:
- [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-configuration-manager-to-configure-catch-up-scans"></a>Usar o Configuration Manager para configurar verificações de captura

1.  Em seu console Microsoft Endpoint Manager, abra a política antimalware que  você deseja alterar (clique em Ativos e Conformidade no painel de navegação à esquerda e expanda a árvore para **Visão** geral  >  **Endpoint Protection**  >  **Políticas antimalware**)

2.  Vá para a seção **Verificações** Agendadas e Force uma verificação do tipo de verificação selecionado se o computador cliente **estiver offline...** para **Sim**. 

3. Clique em **OK**.

4.  [Implantar a política atualizada como de costume](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).

## <a name="related-articles"></a>Artigos relacionados

- [Implantar Microsoft Defender Antivírus](deploy-manage-report-microsoft-defender-antivirus.md)
- [Gerenciar Microsoft Defender Antivírus e aplicar linhas de base](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Gerenciar quando as atualizações de proteção devem ser baixadas e aplicadas](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [Gerenciar atualizações aplicadas com base em evento](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Gerenciar atualizações para dispositivos móveis e máquinas virtuais (VMs)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)