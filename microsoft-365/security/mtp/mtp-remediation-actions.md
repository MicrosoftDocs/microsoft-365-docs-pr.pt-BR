---
title: Ações de correção após as investigações automatizadas no Microsoft Threat Protection
description: Obter uma visão geral das ações de correção que seguem as investigações automatizadas no Microsoft Threat Protection
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
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: ca0c557de24320692d903a1136fc434d635f0507
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955586"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a>Ações de correção após as investigações automatizadas no Microsoft Threat Protection

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft


## <a name="remediation-actions"></a>Ações de correção

Durante e após uma investigação automatizada da proteção contra ameaças da Microsoft, as ações de correção são identificadas para itens mal-intencionados ou suspeitos. Alguns tipos de ações de correção são executadas em dispositivos, também chamados de pontos de extremidade. Outras ações de correção são executadas no conteúdo do email. Investigações automatizadas concluídas depois que as ações de correção são tomadas, aprovadas ou rejeitadas.

A tabela a seguir resume as ações de correção que atualmente têm suporte na proteção contra ameaças da Microsoft: 

|Ações de correção de dispositivo (ponto de extremidade)  |Ações de correção de email  |
|---------|---------|
|Arquivo de quarentena<br/>Remover chave do registro<br/>Finalizar processo <br/>Parar serviço <br/>Desabilitar o driver <br/>Remover tarefa agendada      |Exclusão reversível de mensagens de emails ou clusters<br/>Bloquear URL (hora do clique)<br/>Desativar o encaminhamento de emails externo          |

Ações de correção, se estão aguardando aprovação ou já estão concluídas, podem ser exibidas na [central de ações](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).

## <a name="remediation-actions-follow-automated-investigations"></a>As ações de correção seguem investigações automatizadas

Quando uma investigação automatizada for concluída, um veredito será feito para cada evidência envolvida, e as ações de correção serão identificadas. Em alguns casos, as ações de correção são executadas automaticamente, em outros casos, as ações de correção aguardam aprovação. A tabela a seguir lista os possíveis verditos e resultados:

|Verdito    |Área    |Resultados|
|------|------|------|
|Mal-intencionado    |Dispositivos (pontos de extremidade)    |As ações de correção são tomadas automaticamente|
|Mal-intencionado    |Conteúdo do email (URLs ou anexos) | As ações de correção recomendadas estão aguardando aprovação|
|Suspeito    |Conteúdo de dispositivos ou emails |As ações de correção recomendadas estão aguardando aprovação|
|Nenhuma ameaça encontrada    |Conteúdo de dispositivos ou emails    |Nenhuma ação de correção é necessária|

[Revisar uma ação pendente na Central de Ações](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> Se você acha que algo foi perdido ou detectado incorretamente por recursos de investigação e resposta automatizados na proteção contra ameaças da Microsoft, vamos nos lembrar! [Relatar falsos positivos/negativos](mtp-autoir-report-false-positives-negatives.md).

## <a name="next-steps"></a>Próximas etapas

- [Aprovar ou rejeitar ações](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [Saiba mais sobre a Central de Ações](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
