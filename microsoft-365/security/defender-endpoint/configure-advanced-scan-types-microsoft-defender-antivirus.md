---
title: Configurar opções de verificação para o Microsoft Defender AV
description: Você pode configurar o Microsoft Defender AV para examinar arquivos de armazenamento de email, fazer o back-up ou reparparar pontos, arquivos de rede e arquivos arquivados (como arquivos .zip).
keywords: verificações avançadas, verificação, email, arquivo morto, zip, rar, archive, reparse scanning
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 625c84e79efe53cae2bc8f511726ad3f384ea505
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689825"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>Configurar opções de verificação do Microsoft Defender Antivírus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>Usar o Microsoft Intune para configurar opções de verificação

Consulte [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and Microsoft Defender [Antivírus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) para obter mais detalhes.

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>Usar o Microsoft Endpoint Manager para configurar opções de verificação

Consulte [Como criar e implantar políticas antimalware: Verificar](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) configurações para obter detalhes sobre como configurar o Microsoft Endpoint Manager (branch atual).

## <a name="use-group-policy-to-configure-scanning-options"></a>Usar a Política de Grupo para configurar opções de verificação

Para configurar as configurações da Política de Grupo descritas na tabela a seguir:

1. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e clique em Modelos **administrativos.**

3. Expanda a árvore **para componentes do Windows > o Microsoft Defender Antivírus** e, em seguida, o **Local** especificado na tabela abaixo.

4. Clique duas vezes na **configuração de** política, conforme especificado na tabela abaixo, e de definir a opção para a configuração desejada. Clique **em OK** e repita para quaisquer outras configurações.

Descrição | Local e configuração | Configuração padrão (se não estiver configurada) | Parâmetro PowerShell `Set-MpPreference` ou propriedade WMI para `MSFT_MpPreference` classe
---|---|---|---
Verificação de email Consulte [Limitações de verificação de email](#ref1)| Verificar > Ativar a verificação de email | Desabilitada | `-DisableEmailScanning`
Verificar [pontos de repare](/windows/win32/fileio/reparse-points) | Verificar > Ativar a verificação de ponto de repare | Desabilitada | Não disponível
Examinar unidades de rede mapeadas | Verificar > Executar a verificação completa em unidades de rede mapeadas | Desabilitada | `-DisableScanningMappedNetworkDrivesForFullScan`
 Examinar arquivos de arquivo morto (como arquivos .zip ou .rar). A [lista de exclusão de extensões](configure-extension-file-exclusions-microsoft-defender-antivirus.md) terá precedência sobre essa configuração. | Examinar > arquivos de arquivo morto | Habilitado | `-DisableArchiveScanning`
Examinar arquivos na rede | Examinar > de rede | Desabilitada | `-DisableScanningNetworkFiles`
Examinar executáveis empacotados | Examinar > Executáveis empacotados | Habilitado | Não disponível
Examinar unidades removíveis somente durante verificações completas | Examinar > Verificar unidades removíveis | Desabilitada | `-DisableRemovableDriveScanning`
Especificar o nível de subpastas em uma pasta de arquivo morto a ser digitalizada | Verificar > Especificar a profundidade máxima para examinar arquivos arquivados | 0 | Não disponível
 Especifique a carga máxima da CPU (como porcentagem) durante uma verificação. Observação: este não é um limite rígido, mas uma orientação para que o mecanismo de verificação não exceda esse máximo em média. | Verificação > Especificar o percentual máximo de utilização da CPU durante uma verificação | 50 |  `-ScanAvgCPULoadFactor`
 Especifique o tamanho máximo (em quilobytes) dos arquivos de arquivo morto que devem ser verificados. O padrão, **0**, não aplica limite | Verificação > Especificar o tamanho máximo de arquivos arquivados a serem verificados | Sem limite | Não disponível
 Configurar baixa prioridade de CPU para verificações agendadas | Verificar > Configurar baixa prioridade de CPU para verificações agendadas | Desabilitada | Não disponível
 
> [!NOTE]
> Se a proteção em tempo real estiver acessível, os arquivos serão verificados antes que sejam acessados e executados. O escopo de verificação inclui todos os arquivos, incluindo arquivos em mídia removível montada, como unidades USB. Se o dispositivo que executa a verificação tiver proteção em tempo real ou proteção no acesso, a verificação também incluirá compartilhamentos de rede.

## <a name="use-powershell-to-configure-scanning-options"></a>Usar o PowerShell para configurar opções de verificação

Confira Gerenciar o Microsoft Defender Antivírus com [cmdlets do PowerShell e cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do [Defender](/powershell/module/defender/) para obter mais informações sobre como usar o PowerShell com o Microsoft Defender Antivírus.

## <a name="use-wmi-to-configure-scanning-options"></a>Usar o WMI para configurar opções de verificação

Para usar classes WMI, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

<a id="ref1"></a>

## <a name="email-scanning-limitations"></a>Limitações de verificação de email

A verificação de email permite a verificação de arquivos de email usados pelo Outlook e outros clientes de email durante verificações sob demanda e agendadas. Objetos incorporados em um arquivo de email (como anexos e arquivos arquivados) também são verificados. Os seguintes tipos de formato de arquivo podem ser verificados e remediados:

- DBX
- MBX
- MIME

Os arquivos PST usados pelo Outlook 2003 ou mais antigo (onde o tipo de arquivo morto está definido como não unicode) também serão verificados, mas o Windows Defender não pode correção de ameaças detectadas nos arquivos PST.

Se o Microsoft Defender Antivírus detectar uma ameaça dentro de um email, ele mostrará as seguintes informações para ajudá-lo a identificar o email comprometido, para que você possa correção da ameaça manualmente:

- Assunto do email
- Nome do anexo

## <a name="related-topics"></a>Tópicos relacionados

- [Personalizar, iniciar e revisar os resultados das verificações e correção do Microsoft Defender Antivírus](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Configurar e executar verificações do Microsoft Defender Antivírus sob demanda](run-scan-microsoft-defender-antivirus.md)
- [Configurar verificações agendadas do Microsoft Defender Antivírus](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)