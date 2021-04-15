---
title: Configurar o Microsoft Defender Antivírus com Política de Grupo
description: Saiba como usar uma Política de Grupo para configurar e gerenciar o Microsoft Defender Antivírus em seus pontos de extremidade no Microsoft Defender para Ponto de Extremidade.
keywords: política de grupo, GPO, configuração, configurações
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 04/13/2021
ms.reviewer: ksarens, jtoole, pahuijbr
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: b8122807b8e26a848781f9f66f8e13032345f3fd
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51749909"
---
# <a name="use-group-policy-settings-to-configure-and-manage-microsoft-defender-antivirus"></a>Usar configurações de Política de Grupo para configurar e gerenciar o Microsoft Defender Antivírus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Você pode usar [a Política de Grupo](/windows/win32/srvnodes/group-policy) para configurar e gerenciar o Microsoft Defender Antivírus em seus pontos de extremidade.

Em geral, você pode usar o procedimento a seguir para configurar ou alterar as configurações de política de grupo do Microsoft Defender Antivírus:

1. Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo (GPO) que você deseja configurar e clique em **Editar**.

2. Usando o **Editor de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**

3. Clique **em Modelos Administrativos**.

4. Expanda a árvore para **componentes do Windows**  >  **Microsoft Defender Antivírus**.

5. Expanda a seção (conhecida como **Local** na tabela neste tópico) que contém a configuração que você deseja configurar, clique duas vezes na configuração para abri-la e faça alterações na configuração.

6. [Implante o GPO atualizado como você normalmente faz](/windows/win32/srvnodes/group-policy). 

A tabela a seguir neste tópico lista as configurações da Política de Grupo disponíveis no Windows 10, versão 1703, e fornece links para o tópico apropriado nesta biblioteca de documentação (quando aplicável).

| Local | Setting | Artigo |
|:---|:---|:---|
| Interface do cliente | Habilitar o modo de interface do usuário sem cabeça | [Impedir que os usuários vejam ou interajam com a interface do usuário do Microsoft Defender Antivírus](prevent-end-user-interaction-microsoft-defender-antivirus.md) |
| Interface do cliente | Exibir texto adicional para clientes quando eles precisam executar uma ação | [Configurar as notificações que aparecem nos pontos de extremidade](configure-notifications-microsoft-defender-antivirus.md) |
| Interface do cliente | Suprimir todas as notificações | [Configurar as notificações que aparecem nos pontos de extremidade](configure-notifications-microsoft-defender-antivirus.md) |
| Interface do cliente | Suprime notificações de reinicialização | [Configurar as notificações que aparecem nos pontos de extremidade](configure-notifications-microsoft-defender-antivirus.md) |
| Exclusões | Exclusões de extensão | [Configurar e validar exclusões em verificações do Microsoft Defender Antivírus](configure-exclusions-microsoft-defender-antivirus.md) |
| Exclusões | Exclusões de caminho | [Configurar e validar exclusões em verificações do Microsoft Defender Antivírus](configure-exclusions-microsoft-defender-antivirus.md) |
| Exclusões | Exclusões de processo | [Configurar e validar exclusões em verificações do Microsoft Defender Antivírus](configure-exclusions-microsoft-defender-antivirus.md) | 
| Exclusões | Desativar Exclusões Automáticas | [Configurar e validar exclusões em verificações do Microsoft Defender Antivírus](configure-exclusions-microsoft-defender-antivirus.md) |
| MAPS | Configurar o recurso "Bloquear à Primeira Vista" | [Habilitar o bloqueio à primeira vista](configure-block-at-first-sight-microsoft-defender-antivirus.md) |
| MAPS | Ingressar no Microsoft MAPS | [Habilitar a proteção entregue na nuvem](enable-cloud-protection-microsoft-defender-antivirus.md) |
| MAPS | Enviar amostras de arquivo quando uma análise posterior for necessária | [Habilitar a proteção entregue na nuvem](enable-cloud-protection-microsoft-defender-antivirus.md) |
| MAPS | Configurar a substituição de configuração local para relatórios para o Microsoft MAPS | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| MpEngine | Configurar verificação de nuvem estendida | [Configurar o período de tempo de bloqueio na nuvem](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) |
| MpEngine | Selecionar nível de proteção na nuvem | [Especificar o nível de proteção entregue na nuvem](specify-cloud-protection-level-microsoft-defender-antivirus.md) |
| Sistema de inspeção de rede | Especificar conjuntos de definições adicionais para inspeção de tráfego de rede | Não é mais relevante |
| Sistema de inspeção de rede | Ativar a aposentadoria de definição | Não é mais relevante |
| Sistema de inspeção de rede | Ativar o reconhecimento de protocolo | Não é mais relevante |
| Quarentena | Configurar substituição de configuração local para a remoção de itens da pasta Quarentena | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Quarentena | Configurar a remoção de itens da pasta Quarentena | [Configurar correção para verificações do Microsoft Defender Antivírus](configure-remediation-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Configurar a substituição de configuração local para monitoramento de atividade de arquivo e programa no computador | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Configurar a substituição de configuração local para monitoramento para atividade de arquivo de entrada e saída | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Configurar a substituição de configuração local para verificação de todos os arquivos e anexos baixados | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Configurar a substituição de configuração local para ativar o monitoramento de comportamento | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Configurar a substituição de configuração local para ativar a proteção em tempo real | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Definir o tamanho máximo de arquivos e anexos baixados a serem verificados | [Habilitar e configurar a proteção e o monitoramento always-on do Microsoft Defender Antivírus](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Monitorar atividades de arquivo e programa em seu computador | [Habilitar e configurar a proteção e o monitoramento always-on do Microsoft Defender Antivírus](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Examinar todos os arquivos e anexos baixados | [Habilitar e configurar a proteção e o monitoramento always-on do Microsoft Defender Antivírus](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Desativar a proteção em tempo real | [Habilitar e configurar a proteção e o monitoramento always-on do Microsoft Defender Antivírus](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Ativar o monitoramento de comportamento | [Habilitar e configurar a proteção e o monitoramento always-on do Microsoft Defender Antivírus](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Ativar a verificação de processo sempre que a proteção em tempo real estiver habilitada | [Habilitar e configurar a proteção e o monitoramento always-on do Microsoft Defender Antivírus](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Ativar notificações de gravação de volume bruto | [Habilitar e configurar a proteção e o monitoramento always-on do Microsoft Defender Antivírus](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Proteção em tempo real | Configurar o monitoramento para a atividade de arquivo e programa de entrada e saída | [Habilitar e configurar a proteção e o monitoramento always-on do Microsoft Defender Antivírus](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Correção | Configurar a substituição de configuração local para a hora do dia para executar uma verificação completa agendada para concluir a correção | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Correção | Especificar o dia da semana para executar uma verificação completa agendada para concluir a correção | [Configurar verificações agendadas do Microsoft Defender Antivírus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Correção | Especificar a hora do dia para executar uma verificação completa agendada para concluir a correção | [Configurar verificações agendadas do Microsoft Defender Antivírus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Relatório | Desativar notificações aprimoradas | [Configurar as notificações que aparecem nos pontos de extremidade](configure-notifications-microsoft-defender-antivirus.md)
| Root | Desativar o Microsoft Defender Antivírus | Não usado (Essa configuração deve ser definida como **Não configurada** para garantir que os aplicativos antivírus de terceiros instalados funcionem corretamente)
| Root | Definir endereços para ignorar o servidor proxy | Não usado |
| Root | Definir configuração automática de proxy (.pac) para se conectar à rede | Não usado |
| Root | Definir servidor proxy para se conectar à rede | Não usado |
| Root | Configurar o comportamento de mesclagem de administrador local para listas | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Root | Permitir que o serviço antimalware inicie com prioridade normal | [Configurar correção para verificações do Microsoft Defender Antivírus](configure-remediation-microsoft-defender-antivirus.md) |
| Root | Permitir que o serviço antimalware permaneça em execução sempre | [Configurar correção para verificações do Microsoft Defender Antivírus](configure-remediation-microsoft-defender-antivirus.md) |
| Root | Desativar a correção de rotina | [Configurar correção para verificações do Microsoft Defender Antivírus](configure-remediation-microsoft-defender-antivirus.md) |
| Root | Randomize tempos de tarefa agendados | [Configurar verificações agendadas para o Microsoft Defender Antivírus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Examinar | Permitir que os usuários pausem a verificação | [Impedir que os usuários visem](prevent-end-user-interaction-microsoft-defender-antivirus.md) ou interajam com a interface do usuário do Microsoft Defender Antivírus (Sem suporte no Windows 10) |
| Examinar | Verifique as definições mais recentes de vírus e spyware antes de executar uma verificação agendada | [Gerenciar atualizações forçadas baseadas em eventos](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Examinar | Definir o número de dias após os quais uma verificação de captura é forçada | [Gerenciar atualizações para pontos de extremidade que estão des date](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Examinar | Ativar a verificação completa de captura | [Gerenciar atualizações para pontos de extremidade que estão des date](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Examinar | Ativar a verificação rápida de captura | [Gerenciar atualizações para pontos de extremidade que estão des date](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Examinar | Configurar a substituição de configuração local para o percentual máximo de utilização da CPU | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Examinar | Configurar a substituição de configuração local para o dia da verificação de agendamento | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Examinar | Configurar a substituição de configuração local para o tempo de verificação rápida agendado | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Examinar | Configurar a substituição de configuração local para o tempo de verificação agendado | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Examinar | Configurar a substituição de configuração local para o tipo de verificação a ser usado para uma verificação agendada | [Impedir ou permitir que os usuários modifiquem localmente as configurações de política](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Examinar | Criar um ponto de restauração do sistema | [Configurar correção para verificações do Microsoft Defender Antivírus](configure-remediation-microsoft-defender-antivirus.md) |
| Examinar | Ativar a remoção de itens da pasta histórico de verificação | [Configurar correção para verificações do Microsoft Defender Antivírus](configure-remediation-microsoft-defender-antivirus.md) |
| Examinar | Ativar heurística | [Habilitar e configurar a proteção e o monitoramento always-on do Microsoft Defender Antivírus](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Examinar | Ativar a verificação de email | [Configurar opções de verificação no Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Ativar a verificação de ponto de repare | [Configurar opções de verificação no Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Executar a verificação completa em unidades de rede mapeadas | [Configurar opções de verificação no Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Examinar arquivos arquivados | [Configurar opções de verificação no Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Examinar arquivos de rede | [Configurar opções de verificação no Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Examinar executáveis empacotados | [Configurar opções de verificação no Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Examinar unidades removíveis | [Configurar opções de verificação no Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Especificar a profundidade máxima para examinar arquivos arquivados | [Configurar opções de verificação no Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Especifique o percentual máximo de utilização da CPU durante uma verificação | [Configurar opções de verificação no Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Especificar o tamanho máximo de arquivos arquivados a serem verificados | [Configurar opções de verificação no Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Examinar | Especificar o dia da semana para executar uma verificação agendada | [Configurar verificações agendadas para o Microsoft Defender Antivírus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Examinar | Especificar o intervalo para executar verificações rápidas por dia | [Configurar verificações agendadas para o Microsoft Defender Antivírus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Examinar | Especificar o tipo de verificação a ser usado para uma verificação agendada | [Configurar verificações agendadas para o Microsoft Defender Antivírus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Examinar | Especifique o tempo para uma verificação rápida diária | [Configurar verificações agendadas para o Microsoft Defender Antivírus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Examinar | Especificar a hora do dia para executar uma verificação agendada | [Configurar verificações agendadas para o Microsoft Defender Antivírus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Examinar | Iniciar a verificação agendada somente quando o computador estiver em uso, mas não estiver em uso | [Configurar verificações agendadas para o Microsoft Defender Antivírus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Permitir atualizações de inteligência de segurança do Microsoft Update | [Gerenciar atualizações para dispositivos móveis e máquinas virtuais (VMs)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Permitir atualizações de inteligência de segurança ao executar na energia da bateria | [Gerenciar atualizações para dispositivos móveis e máquinas virtuais (VMs)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Permitir notificações para desabilitar relatórios baseados em definições para o Microsoft MAPS | [Gerenciar atualizações forçadas baseadas em eventos](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Permitir atualizações de inteligência de segurança em tempo real com base em relatórios para o Microsoft MAPS | [Gerenciar atualizações forçadas baseadas em eventos](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Verifique as definições mais recentes de vírus e spyware na inicialização | [Gerenciar atualizações forçadas baseadas em eventos](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Definir compartilhamentos de arquivos para baixar atualizações de inteligência de segurança | [Gerenciar atualizações de inteligência de segurança e proteção do Microsoft Defender Antivírus](manage-protection-updates-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Definir o número de dias após os quais uma atualização de inteligência de segurança de atualização é necessária | [Gerenciar atualizações para pontos de extremidade que estão des date](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Definir o número de dias antes que as definições de spyware sejam consideradas des date | [Gerenciar atualizações para pontos de extremidade que estão des date](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Definir o número de dias antes que as definições de vírus sejam consideradas des date | [Gerenciar atualizações para pontos de extremidade que estão des date](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Definir a ordem das fontes para baixar atualizações de inteligência de segurança | [Gerenciar atualizações de inteligência de segurança e proteção do Microsoft Defender Antivírus](manage-protection-updates-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Iniciar a atualização de inteligência de segurança na inicialização | [Gerenciar atualizações forçadas baseadas em eventos](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Especificar o dia da semana para verificar se há atualizações de inteligência de segurança | [Gerenciar quando as atualizações de proteção devem ser baixadas e aplicadas](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Especifique o intervalo para verificar se há atualizações de inteligência de segurança | [Gerenciar quando as atualizações de proteção devem ser baixadas e aplicadas](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Especifique o tempo para verificar se há atualizações de inteligência de segurança | [Gerenciar quando as atualizações de proteção devem ser baixadas e aplicadas](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| Atualizações de inteligência de segurança | Ativar a verificação após a atualização de Inteligência de Segurança | [Configurar verificações agendadas para o Microsoft Defender Antivírus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Ameaças | Especificar níveis de alerta de ameaça nos quais a ação padrão não deve ser tomada quando detectada | [Configurar correção para verificações do Microsoft Defender Antivírus](configure-remediation-microsoft-defender-antivirus.md) |
| Ameaças | Especificar ameaças sobre as quais a ação padrão não deve ser tomada quando detectada | [Configurar correção para verificações do Microsoft Defender Antivírus](configure-remediation-microsoft-defender-antivirus.md) |


## <a name="related-articles"></a>Artigos relacionados

- [Tópicos de referência para ferramentas de gerenciamento e configuração](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)
