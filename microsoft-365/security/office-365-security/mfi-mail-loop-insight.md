---
title: Visão geral sobre correção de possíveis loop de email
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar a correção de possíveis loops de email no painel de fluxo de emails no centro de conformidade de & de segurança para identificar e corrigir loops de email em sua organização.
ms.openlocfilehash: 162752ce6981e27d6ae2923aeb0fc33aec42bb0f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826948"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Correção de possíveis informações de loop de email no centro de conformidade e segurança &

Um loop de email é ruim porque ele desperdiça recursos do sistema, consome a cota de volume de emails da sua organização e envia notificações confusas de falha na entrega (também conhecidas como NDRs ou mensagens de devolução) para os remetentes originais.

A **correção de possíveis loops de email** na área **recomendada para você** do [painel de fluxo de emails](mail-flow-insights-v2.md) no centro de segurança & conformidade avisa quando um loop de email é detectado em sua organização. Essa percepção aparece apenas após a condição ser detectada (se você não tiver loops de email, não verá a percepção).

![Corrigir recomendações de regras de fluxo de email lentos na área recomendada para você do painel de fluxo de emails](../../media/mfi-fix-possible-mail-loop.png)

Quando você clica em **Exibir detalhes** no widget, um submenu aparece com mais informações:

- **Domínio**
- **Número de mensagens**: você pode clicar em **Exibir exemplos de mensagens** para ver os resultados do [rastreamento](message-trace-scc.md) de mensagens para um exemplo das mensagens que foram afetadas pelo loop.
- **Tipo de domínio**"por exemplo, autoritativo ou não autoritativo.
- **Registro MX**: o host (**servidor de email**) e os valores de **prioridade** do registro MX do domínio.
- **Motivo do loop** e **como corrigir**: tentaremos identificar os cenários de loop de email mais comuns e fornecer as ações recomendadas (se disponível) para corrigir o loop.

![Submenu de detalhes que aparece depois de clicar em Exibir detalhes na correção de possíveis loops de emails](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="related-topics"></a>Tópicos relacionados

Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).
