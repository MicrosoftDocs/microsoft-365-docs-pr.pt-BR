---
title: Bloquear aplicativos potencialmente indesejados com o Microsoft Defender Antivírus
description: Habilite o recurso antivírus de aplicativo potencialmente indesejado (PUA) para bloquear software indesejado, como o adware.
keywords: pua, habilitar, software indesejado, aplicativos indesejados, adware, barra de ferramentas do navegador, detectar, bloquear, Microsoft Defender Antivírus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: fbd897b025db2317dd1c213e5adf5d64ba88e7ac
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275235"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a>Detectar e bloquear aplicativos potencialmente indesejados

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)
- [Microsoft Edge](/microsoft-edge/deploy/microsoft-edge)

Os aplicativos potencialmente indesejados (PUA) são uma categoria de software que pode fazer sua máquina funcionar lentamente, exibir anúncios inesperados ou, pior ainda, instalar outro software inesperado ou indesejado. O PUA não é considerado um vírus, malware ou outro tipo de ameaça, mas pode executar ações nos pontos de extremidade que afetam negativamente o desempenho ou uso do ponto de extremidade. O termo *PUA* também pode se referir a um aplicativo que tem uma reputação ruim, conforme avaliado pelo Microsoft Defender ATP, devido a certos tipos de comportamento indesejável.

Aqui estão alguns exemplos:

- **Software de anúncio** que exibe anúncios ou promoções, incluindo software que insere anúncios em páginas da Web.
- **Software de agrupamento** que oferece a instalação de outro software que não é assinado digitalmente pela mesma entidade. Além disso, o software que oferece a instalação de outro software qualificado como PUA.
- **Software de evasão** que tenta ativamente evitar a detecção por produtos de segurança, incluindo software que se comporta de maneira diferente na presença de produtos de segurança.

> [!TIP]
> Para obter mais exemplos e uma discussão sobre os critérios que usamos para rotular aplicativos a fim de obter atenção especial dos recursos de segurança, confira [Como a Microsoft identifica malware e aplicativos potencialmente indesejados](/windows/security/threat-protection/intelligence/criteria).

Aplicativos potencialmente indesejados podem aumentar o risco de sua rede ser infectada com malware real, dificultar a identificação das infecções por malware ou desperdiçar recursos de TI para limpá-los. A proteção contra PUA tem suporte no Windows 10, Windows Server 2019 e Windows Server 2016. No Windows 10 (versão 2004 e posterior), o Microsoft Defender Antivírus bloqueia os aplicativos considerados PUA para dispositivos Enterprise (E5) por padrão.

## <a name="microsoft-edge"></a>Microsoft Edge

O [novo Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), que é baseado no Chromium, bloqueia downloads de aplicativos potencialmente indesejados e URLs de recursos associados. Este recurso é fornecido por meio do [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a>Habilitar a proteção contra PUA no Microsoft Edge baseado no Chromium

Embora a proteção de aplicativos potencialmente indesejados no Microsoft Edge (baseado no Chromium, versão 80.0.361.50) esteja desativada por padrão, pode ser facilmente ativada a partir do navegador.

1. No navegador Microsoft Edge, selecione as reticências e escolha **Configurações**.

2. Selecione **Privacidade, pesquisa e serviços**.

3. Na seção **Segurança**, ative **Bloquear aplicativos potencialmente indesejados**.

> [!TIP]
> Se estiver executando o Microsoft Edge (baseado no Chromium), você poderá explorar com segurança o recurso de bloqueio de URL da proteção contra PUA testando-o em uma de nossas [páginas de demonstração do Microsoft Defender SmartScreen](https://demo.smartscreen.msft.net/).

### <a name="block-urls-with-microsoft-defender-smartscreen"></a>Bloquear URLs com o Microsoft Defender SmartScreen

No Microsoft Edge baseado no Chromium com a proteção contra PUA ativada, o Microsoft Defender SmartScreen protege você contra URLs associadas ao PUA.

Os administradores de segurança podem [configurar](/DeployEdge/configure-microsoft-edge) como o Microsoft Edge e o Microsoft Defender SmartScreen trabalham juntos para proteger grupos de usuários contra URLs associadas ao PUA. Há várias [configurações de política de grupo](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitamente disponíveis para o Microsoft Defender SmartScreen, incluindo [uma para bloquear o PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled). Além disso, os administradores podem [configurar o Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) como um todo, usando configurações de política de grupo para ativar ou desativar o Microsoft Defender SmartScreen.

Embora o Microsoft Defender ATP tenha sua própria lista de bloqueio com base em um conjunto de dados gerenciado pela Microsoft, você pode personalizar essa lista com base em sua própria inteligência contra ameaças. Se você [criar e gerenciar indicadores](manage-indicators.md) no portal Microsoft Defender ATP, o Microsoft Defender SmartScreen respeitará as novas configurações.

## <a name="microsoft-defender-antivirus-and-pua-protection"></a>Proteção contra PUA e Microsoft Defender Antivírus

O recurso de proteção do aplicativo potencialmente indesejado (PUA) no Microsoft Defender Antivírus detecta e bloqueia o PUA em pontos de extremidade da sua rede.

> [!NOTE]
> Esse recurso está disponível no Windows 10, Windows Server 2019 e Windows Server 2016.

O Microsoft Defender Antivírus bloqueia arquivos PUA detectados e qualquer tentativa de baixar, mover, executar ou instalá-los. Em seguida, os arquivos PUA bloqueados são movidos para a quarentena. Quando um arquivo PUA é detectado em um ponto de extremidade, o Microsoft Defender Antivírus envia uma notificação ao usuário ([a menos que as notificações tenham sido desabilitadas](configure-notifications-microsoft-defender-antivirus.md)) no mesmo formato que outras detecções de ameaças. A notificação é precedida de `PUA:` para indicar seu conteúdo.

A notificação aparece na [lista de quarentena normal dentro do aplicativo Windows Security](microsoft-defender-security-center-antivirus.md).

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a>Configurar a proteção contra PUA no Microsoft Defender Antivírus

Você pode habilitar a proteção contra PUA com o [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Política de Grupo](/azure/active-directory-domain-services/manage-group-policy) ou por meio de [cmdlets do PowerShell](/powershell/module/defender/?preserve-view=true&view=win10-ps).

Você também pode usar a proteção contra PUA no modo de auditoria para detectar aplicativos potencialmente indesejados sem bloqueá-los. As detecções são capturadas no log de eventos do Windows.

> [!TIP]
> Visite o site de demonstração do Microsoft Defender ATP em [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) para confirmar se o recurso está funcionando e vê-lo em ação.

A proteção contra PUA no modo de auditoria é útil se sua empresa estiver realizando uma verificação de conformidade de segurança de software interna, e se você quiser evitar falsos positivos.

### <a name="use-intune-to-configure-pua-protection"></a>Usar o Intune para configurar a proteção contra PUA

Confira [Definir as configurações de restrição de dispositivo no Microsoft Intune](/intune/device-restrictions-configure) e [Configurações de restrição de dispositivo do Microsoft Defender Antivírus para Windows 10 no Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) para obter mais detalhes.

### <a name="use-configuration-manager-to-configure-pua-protection"></a>Usar o Configuration Manager para configurar a proteção contra PUA

A proteção contra PUA está habilitada por padrão no Microsoft Endpoint Manager (Branch Atual).

Confira [Como criar e implantar políticas antimalware: configurações de verificações programadas](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) para obter detalhes sobre a configuração do Microsoft Endpoint Manager (Branch Atual).

Para o System Center 2012 Configuration Manager, confira [Como implantar a Política de Proteção do Aplicativo Potencialmente Indesejado para a Proteção do Ponto de Extremidade no Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).

> [!NOTE]
> Os eventos PUA bloqueados pelo Microsoft Defender Antivírus são relatados no Visualizador de Eventos do Windows e não no Microsoft Endpoint Configuration Manager.

### <a name="use-group-policy-to-configure-pua-protection"></a>Usar a Política de Grupo para configurar a proteção contra PUA

1. Baixe e instale os [Modelos Administrativos (.admx) para a Atualização de outubro de 2020 do Windows 10 (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)

2. No computador de gerenciamento de Política de Grupo, abra o [Console de Gerenciamento de Política de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

3. Selecione o Objeto de Política de Grupo que deseja configurar e escolha **Editar**.

4. No **Editor de Gerenciamento de Política de Grupo**, acesse **Configuração do Computador** e selecione **Modelos Administrativos**.

5. Expanda a árvore para **Componentes do Windows** > **Microsoft Defender Antivírus**.

6. Clique duas vezes em **Configurar a detecção de aplicativos potencialmente indesejados**.

7. Selecione **Habilitado** para habilitar a proteção contra PUA.

8. Em **Opções**, selecione **Bloquear** para bloquear aplicativos potencialmente indesejados ou selecione **Modo de auditoria** para testar como a configuração funciona em seu ambiente. Selecione **OK**.

9. Implante seu objeto de Política de Grupo como de costume.

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a>Usar cmdlets do PowerShell para configurar a proteção contra PUA

#### <a name="to-enable-pua-protection"></a>Para habilitar a proteção contra PUA

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

Definir o valor deste cmdlet para `Enabled` ativa o recurso, caso ele tenha sido desabilitado.

#### <a name="to-set-pua-protection-to-audit-mode"></a>Para definir a proteção contra PUA para o modo de auditoria

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

Definir o `AuditMode` detecta PUAs sem bloqueá-los.

#### <a name="to-disable-pua-protection"></a>Para desabilitar a proteção contra PUA

Recomendamos manter a proteção contra PUA ativada. No entanto, você pode desativá-lo usando o seguinte cmdlet:

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

Definir o valor deste cmdlet para `Disabled` desativa o recurso, caso ele tenha sido habilitado.

Para obter mais informações, confira [Usar cmdlets do PowerShell para configurar e executar o Microsoft Defender Antivírus](use-powershell-cmdlets-microsoft-defender-antivirus.md) e [cmdlets do Defender](/powershell/module/defender/index).

## <a name="view-pua-events-using-powershell"></a>Exibir eventos PUA usando o PowerShell

Os eventos PUA são relatados no Visualizador de Eventos do Windows, mas não no Microsoft Endpoint Manager ou no Intune. Você também pode usar o cmdlet `Get-MpThreat` para visualizar as ameaças manipuladas pelo Microsoft Defender Antivírus. Veja um exemplo:

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

## <a name="get-email-notifications-about-pua-detections"></a>Receber notificações por email sobre detecções de PUA

Você pode ativar as notificações por email para receber emails sobre detecções de PUA.

Confira [Solução de problemas de IDs de eventos](troubleshoot-microsoft-defender-antivirus.md) para obter detalhes sobre a visualização de eventos do Microsoft Defender Antivírus. Os eventos PUA são registrados na ID do evento **1160**.

## <a name="view-pua-events-using-advanced-hunting"></a>Visualizar eventos PUA usando a busca avançada de ameaças

Se estiver usando o [Microsoft Defender ATP](microsoft-defender-endpoint.md), você pode usar uma consulta de busca avançada de ameaças para visualizar eventos PUA. Veja um exemplo de consulta:

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| evaluate bag_unpack(x)
| where ThreatName startswith_cs 'PUA:'
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName, WasExecutingWhileDetected, WasRemediated
```

Para saber mais sobre a busca avançada de ameaças, confira [Buscar proativamente as ameaças com a busca avançada de ameaças](advanced-hunting-overview.md).

## <a name="exclude-files-from-pua-protection"></a>Excluir arquivos da proteção contra PUA

Às vezes, um arquivo é bloqueado erroneamente pela proteção contra PUA ou um recurso de um PUA é necessário para concluir uma tarefa. Nesses casos, é possível adicionar um arquivo a uma lista de exclusão.

Para obter mais informações, confira [Configurar e validar exclusões com base na extensão do arquivo e no local da pasta.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

## <a name="see-also"></a>Confira também

- [Proteção de última geração](microsoft-defender-antivirus-in-windows-10.md)
- [Configurar a proteção comportamental, heurística e em tempo real](configure-protection-features-microsoft-defender-antivirus.md)