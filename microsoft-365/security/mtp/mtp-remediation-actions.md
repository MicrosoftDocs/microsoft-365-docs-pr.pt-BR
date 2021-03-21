---
title: Ações de correção no Microsoft 365 Defender
description: Obter uma visão geral das ações de correção que seguem investigações automatizadas no Microsoft 365 Defender
keywords: automatizado, investigação, alerta, gatilho, ação, correção
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 01/29/2021
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 7dd95e8d7fe6424e294fbc9500fb908819463678
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928623"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Ações de correção no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

## <a name="remediation-actions"></a>Ações de correção

Durante e após uma investigação automatizada no Microsoft 365 Defender, as ações de correção são identificadas para itens mal-intencionados ou suspeitos. Alguns tipos de ações de correção são tomadas em dispositivos, também chamados de pontos de extremidade. Outras ações de correção são tomadas no conteúdo de email. Investigações automatizadas concluídas após ações de correção são tomadas, aprovadas ou rejeitadas.

> [!IMPORTANT]
> Se as ações de correção são tomadas automaticamente ou somente após aprovação depende de determinadas configurações, como os níveis de automação. Para saber mais, confira os seguintes artigos:
> - [Configurar seus recursos automatizados de investigação e resposta no Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)
> - [Como as ameaças são remediadas em dispositivos](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [Ações de ameaças e correção no email & conteúdo de colaboração](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

A tabela a seguir resume as ações de correção com suporte no Microsoft 365 Defender: 

|Ações de correção de dispositivo (ponto de extremidade)  |Ações de correção de email  |
|:---------|:---------|
|- Coletar pacote de investigação <br/>- Isolar dispositivo (essa ação pode ser desfeita)<br/>- Máquina de offboard <br/>- Execução de código de versão <br/>- Liberação da quarentena <br/>- Exemplo de solicitação <br/>- Restringir a execução de código (essa ação pode ser desfeita) <br/>- Executar a verificação antivírus <br/>- Parar e colocar em quarentena      |- Bloquear URL (hora do clique)<br/>- Excluir mensagens de email ou clusters<br/>- Email de quarentena<br/>- Colocar em quarentena um anexo de email<br/>- Desativar o encaminhamento de email externo          |

As ações de correção, sejam aprovações pendentes ou já concluídas, podem ser exibidas no [Centro de Ações](./mtp-action-center.md).

## <a name="remediation-actions-that-follow-automated-investigations"></a>Ações de correção que seguem investigações automatizadas

Quando uma investigação automatizada é concluída, um veredito é atingido para cada prova envolvida. Dependendo do veredito, as ações de correção são identificadas. Em alguns casos, as ações de correção são executadas automaticamente, em outros casos, as ações de correção aguardam aprovação. Tudo depende de como [a investigação e a resposta automatizadas são configuradas.](mtp-configure-auto-investigation-response.md)

A tabela a seguir lista os possíveis verditos e resultados:

| Verdito    | Área    | Resultados|
|------|------|------|
| Mal-intencionado    | Dispositivos (pontos de extremidade)    | As ações de correção são tomadas [](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) automaticamente (supondo que os grupos de dispositivos da sua organização sejam definidos como **Full - correção de ameaças automaticamente**)|
| Mal-intencionado    | Conteúdo do email (URLs ou anexos) | As ações de correção recomendadas estão aguardando aprovação|
| Suspeito    | Conteúdo de dispositivos ou emails | As ações de correção recomendadas estão aguardando aprovação|
| Nenhuma ameaça encontrada    | Conteúdo de dispositivos ou emails    | Nenhuma ação de correção é necessária|


## <a name="remediation-actions-that-are-taken-manually"></a>Ações de correção realizadas manualmente

Além das ações de correção que seguem investigações automatizadas, sua equipe de operações de segurança pode realizar determinadas ações de correção manualmente. Elas incluem as seguintes ações:

- Ação de dispositivo manual, como isolamento de dispositivo ou quarentena de arquivo.
- Ação de email manual, como a exclusão suave de mensagens de email. 
- [Ação de busca](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) avançada em dispositivos ou emails.
- [Ação](../office-365-security/threat-explorer.md) do Explorer no conteúdo de email, como a movimentação de emails para lixo eletrônico, a exclusão de emails ou a exclusão de emails.
- Ação [de resposta ao vivo](/windows/security/threat-protection/microsoft-defender-atp/live-response) manual, como excluir um arquivo, interromper um processo e remover uma tarefa agendada.
- Ação de resposta ao vivo com [APIs](/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)do Microsoft Defender para Ponto de Extremidade , como isolar um dispositivo, executar uma verificação antivírus e obter informações sobre um arquivo. 

## <a name="next-steps"></a>Próximas etapas

- [Visite a Central de Ações](./mtp-action-center.md)
- [Exibir e gerenciar ações de correção](./mtp-autoir-actions.md)
- [Manipular falsos positivos/negativos em recursos automatizados de investigação e resposta](mtp-autoir-report-false-positives-negatives.md)