---
title: Agendar atualizações de proteção do Microsoft Defender Antivírus
description: Agendar o dia, a hora e o intervalo para quando as atualizações de proteção devem ser baixadas
keywords: atualizações, linhas de base de segurança, agendar atualizações
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 327974c4db4166301820cf148811aceda1700513
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765342"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a>Gerenciar o cronograma para quando as atualizações de proteção devem ser baixadas e aplicadas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

O Microsoft Defender Antivírus permite determinar quando ele deve procurar e baixar atualizações.

Você pode agendar atualizações para seus pontos de extremidade por: 

- Especificando o dia da semana para verificar se há atualizações de proteção 
- Especificando o intervalo para verificar se há atualizações de proteção
- Especificando o tempo para verificar se há atualizações de proteção

Você também pode aleatoriamente as horas em que cada ponto de extremidade verifica e baixa atualizações de proteção. Consulte o [tópico Agendar verificações](scheduled-catch-up-scans-microsoft-defender-antivirus.md) para obter mais informações.

## <a name="use-configuration-manager-to-schedule-protection-updates"></a>Usar o Configuration Manager para agendar atualizações de proteção

1.  No console do Microsoft Endpoint Manager, abra a política  antimalware que você deseja alterar (clique em Ativos e Conformidade no painel de navegação à esquerda e expanda a árvore para Visão Geral das Políticas  >    >  **antimalware** de Proteção de Ponto de Extremidade )

2.  Vá para a **seção Atualizações de inteligência de segurança.**

3. Para verificar e baixar atualizações em um determinado momento:
      1. Definir Verificar atualizações de inteligência de segurança da Proteção de Ponto de Extremidade **em um intervalo específico...** como **0**.
      2. Definir Verificar atualizações de inteligência de segurança do **Endpoint Protection diariamente no momento** em que as atualizações devem ser verificadas.
      3
4. Para verificar e baixar atualizações em um intervalo contínuo, Desem conjunto Verificar atualizações de inteligência de segurança da Proteção de Ponto de Extremidade em um intervalo **específico...** para o número de horas que devem ocorrer entre as atualizações.

5.  [Implantar a política atualizada como de costume](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).

## <a name="use-group-policy-to-schedule-protection-updates"></a>Usar a Política de Grupo para agendar atualizações de proteção

> [!IMPORTANT]
> Por padrão, o Microsoft Defender Antivírus verificará se há uma atualização 15 minutos antes da hora de quaisquer verificações agendadas. A habilitação dessas configurações substituirá esse padrão.

1.  Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

3.  No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**

4.  Clique **em Políticas** e modelos **administrativos.**

5.  Expanda a árvore para **componentes do Windows** Atualizações do  >  **Microsoft Defender**  >  **Antivírus Signature Intelligence** e configure as seguintes configurações:

    1. Clique duas vezes **na configuração Especificar o dia** da semana para verificar se há atualizações de inteligência de segurança e de definir a opção como **Habilitado**. Insira o dia da semana para verificar se há atualizações. Clique em **OK**.
    2. Clique duas vezes na **configuração Especificar o intervalo para** verificar se há atualizações de inteligência de segurança e de definir a opção como **Habilitado**. Insira o número de horas entre as atualizações. Clique em **OK**.
    3. Clique duas vezes na **configuração Especificar o horário para** verificar se há atualizações de inteligência de segurança e de definir a opção como **Habilitado**. Insira a hora em que as atualizações devem ser verificadas. O tempo é baseado na hora local do ponto de extremidade. Clique em **OK**.


## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a>Usar cmdlets do PowerShell para agendar atualizações de proteção

Use os seguintes cmdlets:

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md)  do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/) do Microsoft Defender Antivírus e do Defender para obter mais informações sobre como usar o PowerShell com o Microsoft Defender Antivírus.

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a>Usar a Instrução de Gerenciamento do Windows (WMI) para agendar atualizações de proteção

Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

Confira o seguinte para obter mais informações e parâmetros permitidos:
- [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a>Artigos relacionados

- [Implantar o Microsoft Defender Antivírus](deploy-manage-report-microsoft-defender-antivirus.md)
- [Gerenciar atualizações do Microsoft Defender Antivírus e aplicar linhas de base](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Gerenciar atualizações para pontos de extremidade que estão des date](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Gerenciar atualizações aplicadas com base em evento](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Gerenciar atualizações para dispositivos móveis e máquinas virtuais (VMs)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)