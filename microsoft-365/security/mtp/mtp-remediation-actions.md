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
ms.openlocfilehash: e0f76f6a232edeac350d08eeeb47188535ffe688
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502932"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a>Ações de correção após as investigações automatizadas no Microsoft Threat Protection

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft


## <a name="remediation-actions"></a>Ações de correção

Durante e após uma investigação automatizada da proteção contra ameaças da Microsoft, as ações de correção são identificadas para itens mal-intencionados ou suspeitos. Alguns tipos de ações de correção são executadas em dispositivos, também chamados de pontos de extremidade. Outras ações de correção são executadas no conteúdo do email. Investigações automatizadas concluídas depois que as ações de correção são tomadas, aprovadas ou rejeitadas.

A tabela a seguir resume as ações de correção que atualmente têm suporte na proteção contra ameaças da Microsoft: 

|Ações de correção de dispositivo (ponto de extremidade)  |Ações de correção de email  |
|---------|---------|
|– Coletar pacote de investigação <br/>-Isolar dispositivo (esta ação pode ser desfeita)<br/>-Máquina externamente <br/>-Liberar execução de código <br/>– Liberar da quarentena <br/>– Exemplo de solicitação <br/>– Restringir a execução de código (essa ação pode ser desfeita) <br/>– Executar verificação antivírus <br/>– Parar e colocar em quarentena      |-Bloquear URL (tempo de clique)<br/>– Excluir mensagens de email ou clusters<br/>– Email de quarentena<br/>-Colocar um anexo de email em quarentena<br/>– Desativar o encaminhamento de email externo          |

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
