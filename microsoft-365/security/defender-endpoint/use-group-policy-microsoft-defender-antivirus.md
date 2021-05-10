---
title: Configurar Microsoft Defender Antivírus com a Política de Grupo
description: Saiba como usar uma Política de Grupo para configurar e gerenciar Microsoft Defender Antivírus em seus pontos de extremidade no Microsoft Defender para Ponto de Extremidade.
keywords: política de grupo, GPO, configuração, configurações
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/08/2021
ms.reviewer: ksarens, jtoole, pahuijbr
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 74f58959c22313806ebc95aef14e8ccb2d75326b
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52302095"
---
# <a name="use-group-policy-settings-to-configure-and-manage-microsoft-defender-antivirus"></a>Use as configurações da Política de Grupo para configurar e gerenciar Microsoft Defender Antivírus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Você pode usar [a Política de Grupo](/windows/win32/srvnodes/group-policy) para configurar e gerenciar Microsoft Defender Antivírus em seus pontos de extremidade.

## <a name="configure-microsoft-defender-antivirus-using-group-policy"></a>Configurar Microsoft Defender Antivírus usando a Política de Grupo

Em geral, você pode usar o procedimento a seguir para configurar ou alterar Microsoft Defender Antivírus de política de grupo:

1. Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo (GPO) que você deseja configurar e clique em **Editar**.

2. Usando o **Editor de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**

3. Clique **em Modelos Administrativos**.

4. Expanda a árvore para **Windows componentes**  >  **Microsoft Defender Antivírus**.

5. Expanda a seção (conhecida como **Local** na tabela neste tópico) que contém a configuração que você deseja configurar, clique duas vezes na configuração para abri-la e faça alterações na configuração.

6. [Implante o GPO atualizado como você normalmente faz](/windows/win32/srvnodes/group-policy). 

## <a name="group-policy-settings-and-resources"></a>Configurações e recursos da Política de Grupo

A tabela a seguir neste tópico lista as configurações da Política de Grupo disponíveis no Windows 10, versão 1703, e fornece links para o tópico apropriado nesta biblioteca de documentação (quando aplicável). 

> [!TIP]
> Baixe a Planilha de Referência Configurações Política de Grupo para Windows 10 atualização de maio de [2020 (2004)](https://www.microsoft.com/download/101451). Esta planilha lista as configurações de política para configurações do computador e do usuário incluídas nos arquivos de modelo administrativo fornecidos para Windows 10 atualização de maio de 2020 (2004). Você pode configurar consulte a planilha ao editar Objetos de Política de Grupo.

| Local | Configuração | Artigo |
|:---|:---|:---|
| Interface do cliente | Habilitar o modo de interface do usuário sem cabeça | [Impedir que os usuários vejam ou interajam com a Microsoft Defender Antivírus do usuário](prevent-end-user-interaction-microsoft-defender-antivirus.md) |
| Interface do cliente | Exibir texto adicional para clientes quando eles precisam executar uma ação | [Configurar as notificações que aparecem nos pontos de extremidade](configure-notifications-microsoft-defender-antivirus.md) |
| Interface do cliente | Suprimir todas as notificações | [Configurar as notificações que aparecem nos pontos de extremidade](configure-notifications-microsoft-defender-antivirus.md) |
| Interface do cliente | Suprime notificações de reinicialização | [Configurar as notificações que aparecem nos pontos de extremidade](configure-notifications-microsoft-defender-antivirus.md) |
| Exclusões | Exclusões de extensão | [Configurar e validar exclusões em Microsoft Defender Antivírus verificações](configure-exclusions-microsoft-defender-antivirus.md) |
| Exclusões | Exclusões de caminho | [Configurar e validar exclusões em Microsoft Defender Antivírus verificações](configure-exclusions-microsoft-defender-antivirus.md) |
| Exclusões | Exclusões de processo | [Configurar e validar exclusões em Microsoft Defender Antivírus verificações](configure-exclusions-microsoft-defender-antivirus.md) | 
| Exclusões | Desativar Exclusões Automáticas | [Configurar e validar exclusões em Microsoft Defender Antivírus verificações](configure-exclusions-microsoft-defender-antivirus.md) |
| MAPS | Configurar o recurso "Bloquear à Primeira Vista" | [Habilitar o bloqueio à primeira vista](configure-block-at-first-sight-microsoft-defender-antivirus.md) |
| MAPS | Ingressar no Microsoft MAPS | [Ativar proteção fornecida pela nuvem](enable-cloud-protection-microsoft-defender-antivirus.md) |
| MAPS | Enviar amostras de arquivo quando uma análise posterior for necessária | [Ativar proteção fornecida pela nuvem](enable-cloud-protection-microsoft-defender-antivirus.md) |
| MAPS | Configurar a substituição de configuração local para relatórios para o Microsoft MAPS | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| MpEngine | Configurar verificação de nuvem estendida | [Configurar o período de tempo limite de bloqueio da nuvem](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) |
| MpEngine | Selecionar nível de proteção na nuvem | [Especificar o nível de proteção fornecida na nuvem](specify-cloud-protection-level-microsoft-defender-antivirus.md) |
| Sistema de inspeção de rede | Especificar conjuntos de definições adicionais para inspeção de tráfego de rede | [Especificar conjuntos de definições adicionais para inspeção de tráfego de rede](specify-additional-definitions-network-traffic-inspection-mdav.md) |
| Sistema de inspeção de rede | Ativar a aposentadoria de definição | [Configurar a aposentadoria de definição](turn-on-definition-retirement.md)  |
| Sistema de inspeção de rede | Ativar o reconhecimento de protocolo | [Ativar o reconhecimento de protocolo](turn-on-protocol-recognition.md)  |
| Quarentena | Configurar substituição de configuração local para a remoção de itens da pasta Quarentena | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Quarentena | Configurar a remoção de itens da pasta Quarentena | [Configurar correção para Microsoft Defender Antivírus verificações](configure-remediation-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Configurar a substituição de configuração local para monitoramento de atividade de arquivo e programa no computador | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Configurar a substituição de configuração local para monitoramento para atividade de arquivo de entrada e saída | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Configurar a substituição de configuração local para verificação de todos os arquivos e anexos baixados | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Configurar a substituição de configuração local para ativar o monitoramento de comportamento | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Configurar a substituição de configuração local para ativar a proteção em tempo real | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Definir o tamanho máximo de arquivos e anexos baixados a serem verificados | [Habilitar e configurar Microsoft Defender Antivírus proteção e monitoramento always-on](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Monitorar atividades de arquivo e programa em seu computador | [Habilitar e configurar Microsoft Defender Antivírus proteção e monitoramento always-on](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Examinar todos os arquivos e anexos baixados | [Habilitar e configurar Microsoft Defender Antivírus proteção e monitoramento always-on](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Desativar a proteção em tempo real | [Habilitar e configurar Microsoft Defender Antivírus proteção e monitoramento always-on](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Ativar o monitoramento de comportamento | [Habilitar e configurar Microsoft Defender Antivírus proteção e monitoramento always-on](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Ativar a verificação de processo sempre que a proteção em tempo real estiver habilitada | [Habilitar e configurar Microsoft Defender Antivírus proteção e monitoramento always-on](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Ativar notificações de gravação de volume bruto | [Habilitar e configurar Microsoft Defender Antivírus proteção e monitoramento always-on](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Configurar o monitoramento para a atividade de arquivo e programa de entrada e saída | [Habilitar e configurar Microsoft Defender Antivírus proteção e monitoramento always-on](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Correção | Configurar a substituição de configuração local para a hora do dia para executar uma verificação completa agendada para concluir a correção | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Correção | Especificar o dia da semana para executar uma verificação completa agendada para concluir a correção | [Configurar verificações Microsoft Defender Antivírus agendadas](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Correção | Especificar a hora do dia para executar uma verificação completa agendada para concluir a correção | [Configurar verificações Microsoft Defender Antivírus agendadas](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Reporting | Desativar notificações aprimoradas | [Configurar as notificações que aparecem nos pontos de extremidade](configure-notifications-microsoft-defender-antivirus.md)
| Root | Desativar Microsoft Defender Antivírus | Não usado (Essa configuração deve ser definida como **Não configurada** para garantir que os aplicativos antivírus de terceiros instalados funcionem corretamente)
| Root | Definir endereços para ignorar o servidor proxy | Não usado |
| Root | Definir configuração automática de proxy (.pac) para se conectar à rede | Não usado |
| Root | Definir servidor proxy para se conectar à rede | Não usado |
| Root | Configurar o comportamento de mesclagem de administrador local para listas | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Root | Permitir que o serviço antimalware inicie com prioridade normal | [Configurar correção para Microsoft Defender Antivírus verificações](configure-remediation-microsoft-defender-antivirus.md) |
| Root | Permitir que o serviço antimalware permaneça em execução sempre | [Configurar correção para Microsoft Defender Antivírus verificações](configure-remediation-microsoft-defender-antivirus.md) |
| Root | Desativar a correção de rotina | [Configurar correção para Microsoft Defender Antivírus verificações](configure-remediation-microsoft-defender-antivirus.md) |
| Root | Randomize tempos de tarefa agendados | [Configurar verificações agendadas para Microsoft Defender Antivírus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Examinar | Permitir que os usuários pausem a verificação | [Impedir que os usuários vejam ou interajam](prevent-end-user-interaction-microsoft-defender-antivirus.md) com Microsoft Defender Antivírus interface do usuário (Não há suporte no Windows 10) |
| Examinar | Verifique as definições mais recentes de vírus e spyware antes de executar uma verificação agendada | [Gerenciar atualizações aplicadas com base em evento](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Examinar | Definir o número de dias após os quais uma verificação de captura é forçada | [Gerenciar atualizações para pontos de extremidade que estão des date](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Examinar | Ativar a verificação completa de captura | [Gerenciar atualizações para pontos de extremidade que estão des date](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Examinar | Ativar a verificação rápida de captura | [Gerenciar atualizações para pontos de extremidade que estão des date](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Examinar | Configurar a substituição de configuração local para o percentual máximo de utilização da CPU | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Examinar | Configurar a substituição de configuração local para o dia da verificação de agendamento | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Examinar | Configurar a substituição de configuração local para o tempo de verificação rápida agendado | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Examinar | Configurar a substituição de configuração local para o tempo de verificação agendado | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Examinar | Configurar a substituição de configuração local para o tipo de verificação a ser usado para uma verificação agendada | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Examinar | Criar um ponto de restauração do sistema | [Configurar correção para Microsoft Defender Antivírus verificações](configure-remediation-microsoft-defender-antivirus.md) |
| Examinar | Ativar a remoção de itens da pasta histórico de verificação | [Configurar correção para Microsoft Defender Antivírus verificações](configure-remediation-microsoft-defender-antivirus.md) |
| Examinar | Ativar heurística | [Habilitar e configurar Microsoft Defender Antivírus proteção e monitoramento always-on](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Examinar | Ativar a verificação de email | [Configurar opções de verificação em Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Ativar a verificação de ponto de repare | [Configurar opções de verificação em Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Executar a verificação completa em unidades de rede mapeadas | [Configurar opções de verificação em Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Examinar arquivos arquivados | [Configurar opções de verificação em Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Examinar arquivos de rede | [Configurar opções de verificação em Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Examinar executáveis empacotados | [Configurar opções de verificação em Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Examinar unidades removíveis | [Configurar opções de verificação em Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Especificar a profundidade máxima para examinar arquivos arquivados | [Configurar opções de verificação em Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Especifique o percentual máximo de utilização da CPU durante uma verificação | [Configurar opções de verificação em Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Especificar o tamanho máximo de arquivos arquivados a serem verificados | [Configurar opções de verificação em Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Especificar o dia da semana para executar uma verificação agendada | [Configurar verificações agendadas para Microsoft Defender Antivírus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Examinar | Especificar o intervalo para executar verificações rápidas por dia | [Configurar verificações agendadas para Microsoft Defender Antivírus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Examinar | Especificar o tipo de verificação a ser usado para uma verificação agendada | [Configurar verificações agendadas para Microsoft Defender Antivírus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Examinar | Especifique o tempo para uma verificação rápida diária | [Configurar verificações agendadas para Microsoft Defender Antivírus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Examinar | Especificar a hora do dia para executar uma verificação agendada | [Configurar verificações agendadas para Microsoft Defender Antivírus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Examinar | Iniciar a verificação agendada somente quando o computador estiver em uso, mas não estiver em uso | [Configurar verificações agendadas para Microsoft Defender Antivírus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Permitir atualizações de inteligência de segurança do Microsoft Update | [Gerenciar atualizações para dispositivos móveis e máquinas virtuais (VMs)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Permitir atualizações de inteligência de segurança ao executar na energia da bateria | [Gerenciar atualizações para dispositivos móveis e máquinas virtuais (VMs)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Permitir notificações para desabilitar relatórios baseados em definições para o Microsoft MAPS | [Gerenciar atualizações aplicadas com base em evento](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Permitir atualizações de inteligência de segurança em tempo real com base em relatórios para o Microsoft MAPS | [Gerenciar atualizações aplicadas com base em evento](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Verifique as definições mais recentes de vírus e spyware na inicialização | [Gerenciar atualizações aplicadas com base em evento](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Definir compartilhamentos de arquivos para baixar atualizações de inteligência de segurança | [Gerenciar Microsoft Defender Antivírus de proteção e inteligência de segurança](manage-protection-updates-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Definir o número de dias após os quais uma atualização de inteligência de segurança de atualização é necessária | [Gerenciar atualizações para pontos de extremidade que estão des date](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Definir o número de dias antes que as definições de spyware sejam consideradas des date | [Gerenciar atualizações para pontos de extremidade que estão des date](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Definir o número de dias antes que as definições de vírus sejam consideradas des date | [Gerenciar atualizações para pontos de extremidade que estão des date](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Definir a ordem das fontes para baixar atualizações de inteligência de segurança | [Gerenciar Microsoft Defender Antivírus de proteção e inteligência de segurança](manage-protection-updates-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Iniciar a atualização de inteligência de segurança na inicialização | [Gerenciar atualizações aplicadas com base em evento](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Especificar o dia da semana para verificar se há atualizações de inteligência de segurança | [Gerenciar quando as atualizações de proteção devem ser baixadas e aplicadas](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Especifique o intervalo para verificar se há atualizações de inteligência de segurança | [Gerenciar quando as atualizações de proteção devem ser baixadas e aplicadas](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Especifique o tempo para verificar se há atualizações de inteligência de segurança | [Gerenciar quando as atualizações de proteção devem ser baixadas e aplicadas](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Ativar a verificação após a atualização de Inteligência de Segurança | [Configurar verificações agendadas para Microsoft Defender Antivírus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Ameaças | Especificar níveis de alerta de ameaça nos quais a ação padrão não deve ser tomada quando detectada | [Configurar correção para Microsoft Defender Antivírus verificações](configure-remediation-microsoft-defender-antivirus.md) |
| Ameaças | Especificar ameaças sobre as quais a ação padrão não deve ser tomada quando detectada | [Configurar correção para Microsoft Defender Antivírus verificações](configure-remediation-microsoft-defender-antivirus.md) |

## <a name="see-also"></a>Confira também

- [Tópicos de referência para ferramentas de gerenciamento e configuração](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)
