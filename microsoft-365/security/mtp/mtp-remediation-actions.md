---
title: Ações de correção no Microsoft 365 defender
description: Obter uma visão geral das ações de correção que seguem as investigações automatizadas no Microsoft 365 defender
keywords: automatizado, investigação, alerta, gatilho, ação, correção
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 9e489e3b0100aa138b11d4bfb4ccc8048a2113f4
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683290"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Ações de correção no Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

## <a name="remediation-actions"></a>Ações de correção

Durante e após uma investigação automatizada no Microsoft 365 defender, as ações de correção são identificadas para itens mal-intencionados ou suspeitos. Alguns tipos de ações de correção são executadas em dispositivos, também chamados de pontos de extremidade. Outras ações de correção são executadas no conteúdo do email. Investigações automatizadas concluídas depois que as ações de correção são tomadas, aprovadas ou rejeitadas.

> [!IMPORTANT]
> Se as ações de correção serão realizadas automaticamente ou apenas após a aprovação dependerá de determinadas configurações, como os níveis de automação. Para saber mais, confira os seguintes artigos:
> - [Configure seus recursos de investigação e resposta automatizados no Microsoft 365 defender](mtp-configure-auto-investigation-response.md)
> - [Como as ameaças são corrigidas nos dispositivos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [Ameaças e ações de correção em email & conteúdo de colaboração](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions#threats-and-remediation-actions)

A tabela a seguir resume as ações de correção que atualmente têm suporte no Microsoft 365 defender: 

|Ações de correção de dispositivo (ponto de extremidade)  |Ações de correção de email  |
|---------|---------|
|– Coletar pacote de investigação <br/>-Isolar dispositivo (esta ação pode ser desfeita)<br/>-Máquina externamente <br/>-Liberar execução de código <br/>– Liberar da quarentena <br/>– Exemplo de solicitação <br/>– Restringir a execução de código (essa ação pode ser desfeita) <br/>– Executar verificação antivírus <br/>– Parar e colocar em quarentena      |-Bloquear URL (tempo de clique)<br/>– Excluir mensagens de email ou clusters<br/>– Email de quarentena<br/>-Colocar um anexo de email em quarentena<br/>– Desativar o encaminhamento de email externo          |

Ações de correção, se a aprovação pendente ou já concluída, podem ser exibidas na [central de ações](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).

## <a name="remediation-actions-that-follow-automated-investigations"></a>Ações de correção que seguem investigações automatizadas

Quando uma investigação automatizada é concluída, um veredicto é alcançado para cada evidência envolvida. Dependendo do veredicto, as ações de correção serão identificadas. Em alguns casos, as ações de correção são executadas automaticamente, em outros casos, as ações de correção aguardam aprovação. Tudo isso depende de como a [investigação e a resposta automáticas são configuradas](mtp-configure-auto-investigation-response.md).

A tabela a seguir lista os possíveis verditos e resultados:

| Verdito    | Área    | Resultados|
|------|------|------|
| Mal-intencionado    | Dispositivos (pontos de extremidade)    | As ações de correção são realizadas automaticamente (supondo que os [grupos de dispositivos](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) da sua organização estejam definidos para **corrigir ameaças automaticamente**)|
| Mal-intencionado    | Conteúdo do email (URLs ou anexos) | As ações de correção recomendadas estão aguardando aprovação|
| Suspeito    | Conteúdo de dispositivos ou emails | As ações de correção recomendadas estão aguardando aprovação|
| Nenhuma ameaça encontrada    | Conteúdo de dispositivos ou emails    | Nenhuma ação de correção é necessária|


## <a name="remediation-actions-that-are-taken-manually"></a>Ações de correção realizadas manualmente

Além das ações de correção que seguem investigações automatizadas, a equipe de operações de segurança pode realizar determinadas ações de correção manualmente. Isso inclui as seguintes ações:

- Ação manual do dispositivo, como isolamento de dispositivos ou quarentena de arquivos.
- Ação de email manual, como excluir mensagens de email. 
- Ação [avançada de busca](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) em dispositivos ou email.
- O [Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) ação no conteúdo de email, como mover emails para lixo eletrônico, excluir emails ou excluir emails.
- Ação de [resposta ao vivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) manual, como a exclusão de um arquivo, a interrupção de um processo e a remoção de uma tarefa agendada.
- Ação de resposta ao vivo com [Microsoft defender para APIs de ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis), como isolar um dispositivo, executar uma verificação antivírus e obter informações sobre um arquivo. 

## <a name="next-steps"></a>Próximas etapas

- [Visite a Central de Ações](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Aprovar ou rejeitar ações pendentes](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [Lidar com falsos positivos/negativos em recursos de investigação e resposta automatizados](mtp-autoir-report-false-positives-negatives.md)
