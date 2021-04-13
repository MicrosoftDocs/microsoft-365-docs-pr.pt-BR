---
title: Bloquear aplicativos potencialmente indesejados com o Microsoft Defender Antivírus
description: Habilita o recurso antivírus de aplicativo potencialmente indesejado (PUA) para bloquear softwares indesejados, como o adware.
keywords: pua, habilitar, software indesejado, aplicativos indesejados, adware, barra de ferramentas do navegador, detectar, bloquear, Microsoft Defender Antivírus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
ms.localizationpriority: high
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bee92dfa998596578c27bda579a86776bc77c07b
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689999"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a>Detectar e bloquear aplicativos potencialmente indesejados

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)
- [Microsoft Edge](/microsoft-edge/deploy/microsoft-edge)

> [!NOTE]
> Aplicativos potencialmente indesejados (PUA) são uma categoria de software que pode fazer com que seu computador seja executado lentamente, exibir anúncios inesperados ou, na pior das hipóteses, instalar outros softwares que podem ser inesperados ou indesejados. Por padrão, no Windows 10 (versão 2004 e posterior), o Microsoft Defender Antivírus bloqueia aplicativos que são considerados PUA, para dispositivos Enterprise (E5).

Aplicativos potencialmente indesejados (PUA) não são considerados vírus, malware ou outros tipos de ameaças, mas podem executar ações em pontos de extremidade que afetam adversamente o desempenho ou o uso do ponto de extremidade. _O PUA_ também pode se referir a um aplicativo que tem uma reputação ruim, conforme avaliado pelo Microsoft Defender para Ponto de Extremidade, devido a determinados tipos de comportamento indesejável.

Aqui estão alguns exemplos:

- **Software de publicidade** que exibe anúncios ou promoções, incluindo software que insere anúncios em páginas da Web.
- **Software de grupo** que oferece para instalar outros softwares que não são assinados digitalmente pela mesma entidade. Além disso, software que oferece para instalar outros softwares que se qualificam como PUA.
- **Software de evasão** que tenta ativamente evitar a detecção por produtos de segurança, incluindo softwares que se comportam de forma diferente na presença de produtos de segurança.

> [!TIP]
> Para obter mais exemplos e uma discussão sobre os critérios que usamos para rotular aplicativos para atenção especial de recursos de segurança, consulte Como a Microsoft identifica malware e aplicativos potencialmente [indesejados.](/windows/security/threat-protection/intelligence/criteria)

Aplicativos potencialmente indesejados podem aumentar o risco de sua rede ser infectado por malware real, tornar as infecções de malware mais difíceis de identificar ou desperdiçar recursos de IT na limpeza. A proteção pua é suportada no Windows 10, no Windows Server 2019 e no Windows Server 2016.

## <a name="microsoft-edge"></a>Microsoft Edge

O [novo Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), baseado em Chromium, bloqueia downloads de aplicativos potencialmente indesejados e URLs de recursos associados. Esse recurso é fornecido por meio [do Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a>Habilitar a proteção pua no Microsoft Edge baseado em Chromium

Embora a proteção de aplicativo potencialmente indesejada no Microsoft Edge (baseada em Chromium, versão 80.0.361.50) está desligada por padrão, ela pode ser facilmente 2016 a partir do navegador.

1. Selecione as releições e, em seguida, escolha **Configurações**.
2. Selecione **Privacidade, pesquisa e serviços.**
3. Na seção **Segurança,** a turn on **Block potentially unwanted apps**.

> [!TIP]
> Se você estiver executando o Microsoft Edge (baseado em Chromium), poderá explorar com segurança o recurso de bloqueio de URL da proteção PUA testando-o em uma de nossas páginas de demonstração do [Microsoft Defender SmartScreen.](https://demo.smartscreen.msft.net/)

### <a name="blocking-urls-with-microsoft-defender-smartscreen"></a>Bloqueando URLs com o Microsoft Defender SmartScreen

No Edge baseado em Chromium com a proteção PUA ligada, o Microsoft Defender SmartScreen protege você contra URLs associadas a PUA.

Os administradores de segurança podem [configurar](/DeployEdge/configure-microsoft-edge) como o Microsoft Edge e o Microsoft Defender SmartScreen trabalham juntos para proteger grupos de usuários de URLs associadas a PUA. Há várias [configurações de política de grupo](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitamente para o Microsoft Defender SmartScreen disponíveis, incluindo uma para bloquear [PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled). Além disso, os administradores podem configurar o [Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) como um todo, usando as configurações de política de grupo para ativar ou desativar o Microsoft Defender SmartScreen.

Embora o Microsoft Defender para Ponto de Extremidade tenha sua própria lista de bloqueios com base em um conjunto de dados gerenciado pela Microsoft, você pode personalizar essa lista com base em sua própria inteligência contra ameaças. Se você [criar e gerenciar indicadores](/microsoft-365/security/defender-endpoint/manage-indicators) no portal do Microsoft Defender para Ponto de Extremidade, o Microsoft Defender SmartScreen respeitará as novas configurações.

## <a name="microsoft-defender-antivirus"></a>Microsoft Defender Antivírus

O recurso de proteção de aplicativos potencialmente indesejados (PUA) no Microsoft Defender Antivírus pode detectar e bloquear PUAs em pontos de extremidade em sua rede.

> [!NOTE]
> Esse recurso está disponível no Windows 10, no Windows Server 2019 e no Windows Server 2016.

O Microsoft Defender Antivírus bloqueia arquivos PUA detectados e qualquer tentativa de baixar, mover, executar ou instalá-los. Os arquivos PUA bloqueados são movidos para quarentena. Quando um arquivo PUA é detectado em um ponto de extremidade, o Microsoft Defender Antivírus envia uma notificação para o usuário[(](configure-notifications-microsoft-defender-antivirus.md)a menos que as notificações tenham sido desabilitadas ) no mesmo formato que outras detecções de ameaças. A notificação é prefigurada para `PUA:` indicar seu conteúdo.

A notificação aparece na lista de [quarentenas usuais dentro do aplicativo segurança do Windows](microsoft-defender-security-center-antivirus.md).

### <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a>Configurar a proteção pua no Microsoft Defender Antivírus

Você pode habilitar a proteção PUA com [o Microsoft Intune,](/mem/intune/protect/device-protect) [o Microsoft Endpoint Configuration Manager,](/mem/configmgr/protect/deploy-use/endpoint-protection)a Política de Grupo [ou](/azure/active-directory-domain-services/manage-group-policy)por [meio de cmdlets do PowerShell.](/powershell/module/defender/?preserve-view=true&view=win10-ps)

Você também pode usar a proteção PUA no modo de auditoria para detectar aplicativos potencialmente indesejados sem bloqueá-los. As detecções são capturadas no log de eventos do Windows.

> [!TIP]
> Visite o site de demonstração do Microsoft Defender para Ponto de Extremidade no demo.wd.microsoft.com [para](https://demo.wd.microsoft.com/Page/UrlRep) confirmar se o recurso está funcionando e vê-lo em ação.

A proteção pua no modo de auditoria é útil se sua empresa estiver realizando uma verificação de conformidade de segurança de software interna e você quiser evitar falsos positivos.

#### <a name="use-intune-to-configure-pua-protection"></a>Usar o Intune para configurar a proteção pua

Consulte [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and Microsoft Defender [Antivírus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) para obter mais detalhes.

#### <a name="use-configuration-manager-to-configure-pua-protection"></a>Usar o Configuration Manager para configurar a proteção pua

A proteção pua é habilitada por padrão no Microsoft Endpoint Manager (Branch Atual).

Consulte [Como criar e implantar políticas antimalware: Configurações](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) de verificações agendadas para obter detalhes sobre como configurar o Microsoft Endpoint Manager (Branch Atual).

Para o System Center 2012 Configuration Manager, consulte [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).

> [!NOTE]
> Os eventos PUA bloqueados pelo Microsoft Defender Antivírus são relatados no Visualizador de Eventos do Windows e não no Microsoft Endpoint Configuration Manager.

#### <a name="use-group-policy-to-configure-pua-protection"></a>Usar a Política de Grupo para configurar a proteção pua

1. Baixar e instalar [Modelos Administrativos (.admx) para Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)

2. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política [de Grupo.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

3. Selecione o Objeto de Política de Grupo que você deseja configurar e escolha **Editar**.

4. No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e selecione Modelos **administrativos.**

5. Expanda a árvore para **Componentes do Windows**  >  **Microsoft Defender Antivírus**.

6. Clique duas vezes em **Configurar detecção para aplicativos potencialmente indesejados.**

7. Selecione **Habilitado para** habilitar a proteção PUA.

8. Em **Opções,** selecione **Bloquear** para bloquear aplicativos potencialmente indesejados ou selecione **Modo** de Auditoria para testar como a configuração funciona em seu ambiente. Clique em **OK**.

9. Implante seu objeto de Política de Grupo como você costuma fazer.

#### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a>Usar cmdlets do PowerShell para configurar a proteção PUA

##### <a name="to-enable-pua-protection"></a>Para habilitar a proteção pua

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

A definição do valor desse cmdlet para `Enabled` aticá-lo se tiver sido desabilitado.

##### <a name="to-set-pua-protection-to-audit-mode"></a>Para definir a proteção pua como modo de auditoria

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

A `AuditMode` configuração detecta PUAs sem bloqueá-los.

##### <a name="to-disable-pua-protection"></a>Para desabilitar a proteção pua

Recomendamos manter a proteção PUA 2016 2016. No entanto, você pode desativar usando o seguinte cmdlet:

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

Definir o valor desse cmdlet para `Disabled` desligar o recurso se tiver sido habilitado.

Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/index) do Microsoft Defender Antivírus e do Defender para obter mais informações sobre como usar o PowerShell com o Microsoft Defender Antivírus.

## <a name="view-pua-events"></a>Exibir eventos PUA

Os eventos PUA são relatados no Visualizador de Eventos do Windows, mas não no Microsoft Endpoint Manager ou no Intune. Você também pode usar o `Get-MpThreat` cmdlet para exibir as ameaças que o Microsoft Defender Antivírus lidou. Exemplo:

```console
CategoryID       : 27
DidThreatExecute : False
IsActive         : False
Resources        : {webfile:_q:\Builds\Dalton_Download_Manager_3223905758.exe|http://d18yzm5yb8map8.cloudfront.net/
                    fo4yue@kxqdw/Dalton_Download_Manager.exe|pid:14196,ProcessStart:132378130057195714}
RollupStatus     : 33
SchemaVersion    : 1.0.0.0
SeverityID       : 1
ThreatID         : 213927
ThreatName       : PUA:Win32/InstallCore
TypeID           : 0
PSComputerName   :
```

Você pode ativar notificações por email para receber emails sobre detecções de PUA.

Consulte [Solucionar problemas de IDs de eventos](troubleshoot-microsoft-defender-antivirus.md) para obter detalhes sobre como exibir eventos do Microsoft Defender Antivírus. Os eventos PUA são registrados na ID do evento **1160**.

## <a name="excluding-files"></a>Excluindo arquivos

Às vezes, um arquivo é bloqueado erroneamente pela proteção pua ou um recurso de pua é necessário para concluir uma tarefa. Nesses casos, um arquivo pode ser adicionado a uma lista de exclusão.

Para obter mais informações, [consulte Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).

## <a name="see-also"></a>Confira também

- [Proteção de próxima geração](microsoft-defender-antivirus-in-windows-10.md)
- [Configurar proteção comportamental, heurística e em tempo real](configure-protection-features-microsoft-defender-antivirus.md)