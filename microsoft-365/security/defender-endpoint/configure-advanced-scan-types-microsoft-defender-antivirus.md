---
title: Configurar opções de verificação para Microsoft Defender Antivírus
description: Você pode configurar o Microsoft Defender AV para examinar arquivos de armazenamento de email, fazer o back-up ou analisar novamente pontos, arquivos de rede e arquivos arquivados (como arquivos .zip de email).
keywords: verificações avançadas, verificação, email, arquivo morto, zip, rar, archive, reparse scanning
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.date: 05/26/2021
ms.topic: how-to
ms.openlocfilehash: 34f423222068236271afdda13afb95cffa58b709
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683806"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>Configurar opções de verificação do Microsoft Defender Antivírus

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>Usar Microsoft Intune para configurar opções de verificação

Consulte os seguintes recursos: 

- [Configurar configurações de restrição de dispositivos Microsoft Intune](/intune/device-restrictions-configure) 
- [Microsoft Defender Antivírus configurações de restrição de dispositivo para Windows 10 no Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>Usar Microsoft Endpoint Manager para configurar opções de verificação

Consulte [Como criar e implantar políticas antimalware: Verificar configurações](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings).

## <a name="use-group-policy-to-configure-scanning-options"></a>Usar a Política de Grupo para configurar opções de verificação

1. No computador de gerenciamento de Política de Grupo, abra o [Console de Gerenciamento de Política de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.

3. No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e clique em Modelos **administrativos.**

4. Expanda a árvore para **Windows componentes** Microsoft Defender Antivírus e selecione um local (consulte Configurações  >   [e locais](#settings-and-locations) neste artigo).

5. Edite o objeto policy. 

6. Clique **em OK** e repita para quaisquer outras configurações.

### <a name="settings-and-locations"></a>Configurações e locais

| Item e local da política | Configuração padrão (se não estiver configurada) | Parâmetro PowerShell `Set-MpPreference` ou propriedade WMI para `MSFT_MpPreference` classe |
|---|---|---|
| Verificação de email <p> **Verificação**  >  **Ativar a verificação de email**<p>Consulte [Limitações de verificação de email](#email-scanning-limitations) (neste artigo) | Desabilitado | `-DisableEmailScanning` |
|Verificar [pontos de repare](/windows/win32/fileio/reparse-points) <p> **Verificação**  >  **Ativar a verificação de ponto de repare** | Desabilitado | Não disponível <p>Consulte [Pontos de repare](/windows/win32/fileio/reparse-points)  |
| Examinar unidades de rede mapeadas <p> **Verificação**  >  **Executar a verificação completa em unidades de rede mapeadas** | Desabilitado | `-DisableScanningMappedNetworkDrivesForFullScan`|
| Examinar arquivos arquivados (como arquivos .zip ou .rar arquivos).  <p> **Verificação**  >  **Examinar arquivos arquivados** | Habilitado | `-DisableArchiveScanning` <p>A [lista de exclusão de extensões](configure-extension-file-exclusions-microsoft-defender-antivirus.md) terá precedência sobre essa configuração.|
| Examinar arquivos na rede <p> **Verificação**  >  **Examinar arquivos de rede** | Desabilitado | `-DisableScanningNetworkFiles` |
| Examinar executáveis empacotados <p> **Verificação**  >  **Examinar executáveis empacotados** | Habilitado | Não disponível |
| Examinar unidades removíveis somente durante verificações completas <p> **Verificação**  >  **Examinar unidades removíveis** | Desabilitado | `-DisableRemovableDriveScanning` |
| Especificar o nível de subpastas em uma pasta de arquivo morto a ser digitalizada <p>**Verificação**  >  **Especificar a profundidade máxima para examinar arquivos arquivados** | 0 | Não disponível |
| Especifique a carga máxima da CPU (como porcentagem) durante uma verificação. <p> **Verificação**  >  **Especifique o percentual máximo de utilização da CPU durante uma verificação** | 50 |  `-ScanAvgCPULoadFactor` <p>**OBSERVAÇÃO**: a carga máxima da CPU não é um limite rígido, mas é orientação para que o mecanismo de verificação não exceda o máximo em média. As verificações de executar manualmente ignorarão essa configuração e serão executados sem limites de CPU. |
| Especifique o tamanho máximo (em quilobytes) dos arquivos de arquivo morto que devem ser verificados. <p> **Verificação**  >  **Especificar o tamanho máximo de arquivos arquivados a serem verificados** | Sem limite | Não disponível <p>O valor padrão de 0 não aplica limite |
| Configurar baixa prioridade de CPU para verificações agendadas <p> **Verificação**  >  **Configurar baixa prioridade de CPU para verificações agendadas** | Desabilitado | Não disponível |
 
> [!NOTE]
> Se a proteção em tempo real estiver acessível, os arquivos serão verificados antes que sejam acessados e executados. O escopo de verificação inclui todos os arquivos, incluindo arquivos em mídia removível montada, como unidades USB. Se o dispositivo que executa a verificação tiver proteção em tempo real ou proteção no acesso, a verificação também incluirá compartilhamentos de rede.

## <a name="use-powershell-to-configure-scanning-options"></a>Usar o PowerShell para configurar opções de verificação

Consulte os seguintes recursos:

- [Gerenciar Microsoft Defender Antivírus com cmdlets do PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Cmdlets defender](/powershell/module/defender/)

## <a name="use-wmi-to-configure-scanning-options"></a>Usar o WMI para configurar opções de verificação

Consulte [Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

## <a name="email-scanning-limitations"></a>Limitações de verificação de email

A verificação de email permite a verificação de arquivos de email usados por Outlook e outros clientes de email durante verificações sob demanda e agendadas. Objetos incorporados no email (como anexos e arquivos arquivados) também são verificados. Os seguintes tipos de formato de arquivo podem ser verificados e remediados:

- DBX
- MBX
- MIME

Os arquivos PST usados pelo Outlook 2003 ou mais antigo (onde o tipo de arquivo morto está definido como não unicode) também são verificados, mas o Microsoft Defender Antivírus não pode correção de ameaças detectadas dentro de arquivos PST.

Se Microsoft Defender Antivírus detectar uma ameaça dentro de uma mensagem de email, ele mostrará as seguintes informações para ajudá-lo a identificar o email comprometido, para que você possa correção da ameaça manualmente:

- Assunto do email
- Nome do anexo

## <a name="see-also"></a>Confira também

- [Personalizar, iniciar e revisar os resultados de Microsoft Defender Antivírus e correção](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Configurar e executar verificações do Microsoft Defender Antivírus sob demanda](run-scan-microsoft-defender-antivirus.md)
- [Configurar verificações Microsoft Defender Antivírus agendadas](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)
