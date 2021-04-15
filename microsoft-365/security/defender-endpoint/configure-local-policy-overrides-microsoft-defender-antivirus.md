---
title: Configurar substituições locais para configurações do Microsoft Defender AV
description: Habilitar ou desabilitar usuários de configurações de alteração local no Microsoft Defender AV.
keywords: substituição local, política local, política de grupo, gpo, bloqueio, mesclagem, listas
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 02/13/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f3c2b7ae70f42cb7ffc2deef1786ad43e65f33b6
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764634"
---
# <a name="prevent-or-allow-users-to-locally-modify-microsoft-defender-antivirus-policy-settings"></a>Impedir ou permitir que os usuários modifiquem localmente as configurações de política do Microsoft Defender Antivírus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Por padrão, as configurações do Microsoft Defender Antivírus implantadas por meio de um Objeto de Política de Grupo para os pontos de extremidade em sua rede impedirão que os usuários mudem localmente as configurações. Você pode alterar isso em algumas instâncias.

Por exemplo, pode ser necessário permitir que determinados grupos de usuários (como pesquisadores de segurança e investigadores de ameaças) controlem ainda mais as configurações individuais nos pontos de extremidade que usam.

## <a name="configure-local-overrides-for-microsoft-defender-antivirus-settings"></a>Configurar substituições locais para configurações do Microsoft Defender Antivírus

A configuração padrão para essas políticas é **Disabled**.

Se eles estão definidos como **Habilitados**, os usuários nos pontos de extremidade podem fazer alterações na configuração associada ao aplicativo segurança do [Windows,](microsoft-defender-security-center-antivirus.md) configurações locais da Política de Grupo e cmdlets do PowerShell (quando apropriado).

A tabela a seguir lista cada uma das configurações de política de substituição e as instruções de configuração para o recurso ou configuração associado.

Para configurar essas configurações:

1. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e clique em Modelos **administrativos.**

3. Expanda a árvore **para componentes do Windows > o Microsoft Defender Antivírus** e, em seguida, o **Local** especificado na tabela abaixo.

4. Clique duas vezes na **configuração de** política, conforme especificado na tabela abaixo, e de definir a opção para a configuração desejada. Clique **em OK** e repita para quaisquer outras configurações.

5. Implante o objeto de Política de Grupo como de costume.

Local | Setting | Artigo
---|---|---|---
MAPS | Configurar a substituição de configuração local para relatórios para o Microsoft MAPS | [Habilitar a proteção entregue na nuvem](enable-cloud-protection-microsoft-defender-antivirus.md)
Quarentena | Configurar substituição de configuração local para a remoção de itens da pasta Quarentena | [Configurar correção para verificações](configure-remediation-microsoft-defender-antivirus.md)
Proteção em tempo real | Configurar a substituição de configuração local para monitoramento de atividade de arquivo e programa no computador | [Habilitar e configurar a proteção e o monitoramento always-on do Microsoft Defender Antivírus](configure-real-time-protection-microsoft-defender-antivirus.md)
Proteção em tempo real | Configurar a substituição de configuração local para monitoramento para atividade de arquivo de entrada e saída | [Habilitar e configurar a proteção e o monitoramento always-on do Microsoft Defender Antivírus](configure-real-time-protection-microsoft-defender-antivirus.md)
Proteção em tempo real | Configurar a substituição de configuração local para verificação de todos os arquivos e anexos baixados | [Habilitar e configurar a proteção e o monitoramento always-on do Microsoft Defender Antivírus](configure-real-time-protection-microsoft-defender-antivirus.md)
Proteção em tempo real | Configurar a substituição de configuração local para ativar o monitoramento de comportamento | [Habilitar e configurar a proteção e o monitoramento always-on do Microsoft Defender Antivírus](configure-real-time-protection-microsoft-defender-antivirus.md)
Proteção em tempo real | Configurar a substituição de configuração local para ativar a proteção em tempo real | [Habilitar e configurar a proteção e o monitoramento always-on do Microsoft Defender Antivírus](configure-real-time-protection-microsoft-defender-antivirus.md)
Correção | Configurar a substituição de configuração local para a hora do dia para executar uma verificação completa agendada para concluir a correção | [Configurar correção para verificações](configure-remediation-microsoft-defender-antivirus.md)
Examinar | Configurar a substituição de configuração local para o percentual máximo de utilização da CPU | [Configurar e executar verificações](run-scan-microsoft-defender-antivirus.md)
Examinar | Configurar a substituição de configuração local para o dia da verificação de agendamento | [Configurar verificações agendadas](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
Examinar | Configurar a substituição de configuração local para o tempo de verificação rápida agendado | [Configurar verificações agendadas](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
Examinar | Configurar a substituição de configuração local para o tempo de verificação agendado | [Configurar verificações agendadas](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
Examinar | Configurar a substituição de configuração local para o tipo de verificação a ser usado para uma verificação agendada | [Configurar verificações agendadas](scheduled-catch-up-scans-microsoft-defender-antivirus.md)

<a id="merge-lists"></a>

## <a name="configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged"></a>Configurar como as listas de correção e exclusões de ameaças definidas localmente e globalmente são mescladas

Você também pode configurar como as listas definidas localmente são combinadas ou mescladas com listas definidas globalmente. Essa configuração se aplica a listas [de exclusão,](configure-exclusions-microsoft-defender-antivirus.md)listas de [correção especificadas](configure-remediation-microsoft-defender-antivirus.md)e [redução de superfície de ataque.](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)

Por padrão, as listas que foram configuradas na política de grupo local e o aplicativo segurança do Windows são mescladas com listas definidas pelo Objeto de Política de Grupo apropriado que você implantou em sua rede. Onde há conflitos, a lista globalmente definida tem precedência.

Você pode desabilitar essa configuração para garantir que apenas listas definidas globalmente (como aquelas de qualquer GPOs implantado) sejam usadas.

### <a name="use-group-policy-to-disable-local-list-merging"></a>Usar a Política de Grupo para desabilitar a mesclação de listas locais

1. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e clique em Modelos **administrativos.**

3. Expanda a árvore para **componentes do Windows > Microsoft Defender Antivírus**.

4. Clique duas vezes em **Configurar o comportamento de mesclagem de** administrador local para listas e de definir a opção como **Desabilitada**. Clique em **OK**.

> [!NOTE]
> Se você desabilitar a mesclação de lista local, ela substituirá as configurações de acesso controlado a pastas. Ele também substitui todas as pastas protegidas ou aplicativos permitidos definidos pelo administrador local. Para obter mais informações sobre configurações de acesso controlado a pastas, consulte [Permitir um aplicativo bloqueado no Windows Security](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security).

## <a name="related-topics"></a>Tópicos relacionados

- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Configurar a interação do usuário final com o Microsoft Defender Antivírus](configure-end-user-interaction-microsoft-defender-antivirus.md)