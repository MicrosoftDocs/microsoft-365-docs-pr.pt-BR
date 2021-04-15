---
title: Configurar a remediação para detecções do Microsoft Defender Antivírus
description: Configure o que o Microsoft Defender Antivírus deve fazer quando detectar uma ameaça e por quanto tempo os arquivos em quarentena devem ser mantidos na pasta de quarentena
keywords: correção, correção, remoção, ameaças, quarentena, verificação, restauração
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 03/16/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 98bc079bcfd772ada52d699d5f873a187d4ab4c1
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765054"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a>Configurar a remediação para detecções do Microsoft Defender Antivírus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Quando o Microsoft Defender Antivírus executa uma verificação, ele tenta remediar ou remover ameaças detectadas. Você pode configurar como o Microsoft Defender Antivírus deve lidar com determinadas ameaças, se um ponto de restauração deve ser criado antes da correção e quando as ameaças devem ser removidas.

Este artigo descreve como configurar essas configurações usando a Política de Grupo, mas você também pode usar o [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) e o Microsoft [Intune](/intune/device-restrictions-configure). 

Você também pode usar o [ `Set-MpPreference` cmdlet do PowerShell](/powershell/module/defender/set-mppreference) ou a [ `MSFT_MpPreference` classe WMI](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) para configurar essas configurações.

## <a name="configure-remediation-options"></a>Configurar opções de correção

1. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e selecione Modelos **administrativos.**

3. Expanda a árvore para **componentes do Windows**  >  **Microsoft Defender Antivírus**. 

4. Usando a tabela abaixo, selecione um local e edite a política conforme necessário. 

5. Clique em **OK**.

|Local | Setting | Descrição | Configuração padrão (se não estiver configurada) |
|:---|:---|:---|:---|
|Examinar | Criar um ponto de restauração do sistema | Um ponto de restauração do sistema será criado todos os dias antes da tentativa de limpeza ou verificação | Desabilitada|
|Examinar | Ativar a remoção de itens da pasta histórico de verificação | Especificar quantos itens de dias devem ser mantidos no histórico de verificação | 30 dias |
|Root | Desativar a correção de rotina | Você pode especificar se o Microsoft Defender Antivírus corrigiu automaticamente as ameaças ou se ele deve perguntar ao usuário do ponto de extremidade o que fazer. | Desabilitada (as ameaças são corrigidas automaticamente) |
|Quarentena | Configurar a remoção de itens da pasta Quarentena | Especificar quantos itens de dias devem ser mantidos em quarentena antes de serem removidos | 90 dias |
|Ameaças | Especificar níveis de alerta de ameaça nos quais a ação padrão não deve ser tomada quando detectada | Todas as ameaças detectadas pelo Microsoft Defender Antivírus são atribuídas a um nível de ameaça (baixo, médio, alto ou grave). Você pode usar essa configuração para definir como todas as ameaças para cada um dos níveis de ameaça devem ser remediadas (colocadas em quarentena, removidas ou ignoradas) | Não aplicável |
|Ameaças | Especificar ameaças sobre as quais a ação padrão não deve ser tomada quando detectada | Especifique como ameaças específicas (usando sua ID de ameaça) devem ser remediadas. Você pode especificar se a ameaça específica deve ser colocada em quarentena, removida ou ignorada | Não aplicável |

> [!IMPORTANT]
> O Microsoft Defender Antivírus detecta e remedia arquivos com base em muitos fatores. Às vezes, concluir uma correção requer uma reinicialização. Mesmo que a detecção seja determinada posteriormente como um falso positivo, a reinicialização deve ser concluída para garantir que todas as etapas de correção adicionais tenham sido concluídas.
>
> Se você tiver certeza de que o Microsoft Defender Antivírus colocou um arquivo em quarentena com base em um falso positivo, poderá restaurar o arquivo da quarentena após a reinicialização do dispositivo. Consulte [Restaurar arquivos em quarentena no Microsoft Defender Antivírus](restore-quarantined-files-microsoft-defender-antivirus.md).
> 
> Para evitar esse problema no futuro, você pode excluir arquivos das verificações. Consulte [Configurar e validar exclusões para verificações do Microsoft Defender Antivírus.](configure-exclusions-microsoft-defender-antivirus.md)

Consulte Também [Configure remediation-required scheduled full Microsoft Defender Antivírus scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) for more remediation-related settings.

## <a name="see-also"></a>Confira também

- [Configurar opções de verificação do Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Configurar verificações agendadas do Microsoft Defender Antivírus](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Configurar e executar verificações do Microsoft Defender Antivírus sob demanda](run-scan-microsoft-defender-antivirus.md)
- [Configurar as notificações que aparecem nos pontos de extremidade](configure-notifications-microsoft-defender-antivirus.md)
- [Configurar a interação do Microsoft Defender Antivírus para o usuário final](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [Personalizar, iniciar e revisar os resultados das verificações e correção do Microsoft Defender Antivírus](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)