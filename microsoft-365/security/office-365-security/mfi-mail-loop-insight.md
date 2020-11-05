---
title: Visão geral sobre correção de possíveis loop de email
f1.keywords:
- NOCSH
ms.author: siosulli
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
ms.openlocfilehash: 1d49fd93b2ea068986e003b36077672215a2dd57
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920555"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Correção de possíveis informações de loop de email no centro de conformidade e segurança &

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Os loops de email são ruins porque:

- Eles desperdiçam recursos do sistema.
- Eles consomem a cota de volume de email da sua organização.
- Eles enviam notificações confusas de não entrega (também conhecidas como NDRs ou mensagens de devolução) para os remetentes de mensagens originais.

A **correção de possíveis loops de email** na área **recomendada para você** do [painel de fluxo de emails](mail-flow-insights-v2.md) no [centro de segurança & conformidade](https://protection.office.com) avisa quando um loop de email é detectado em sua organização.

Essa percepção aparece apenas após a condição ser detectada (se você não tiver loops de email, não verá a percepção).

![Corrigir recomendações de regras de fluxo de email lentos na área recomendada para você do painel de fluxo de emails](../../media/mfi-fix-possible-mail-loop.png)

Quando você clica em **Exibir detalhes** no widget, um submenu aparece com mais informações:

- **Domínio**
- **Número de mensagens** : você pode clicar em **Exibir exemplos de mensagens** para ver os resultados do [rastreamento](message-trace-scc.md) de mensagens para um exemplo das mensagens que foram afetadas pelo loop.
- **Tipo de domínio** "por exemplo, autoritativo ou não autoritativo.
- **Registro MX** : o host ( **servidor de email** ) e os valores de **prioridade** do registro MX do domínio.
- **Motivo do loop** e **como corrigir** : identificaremos os cenários de loop de email mais comuns e fornecerão as ações recomendadas para corrigir o loop.

![Submenu de detalhes que aparece depois de clicar em Exibir detalhes na correção de possíveis loops de emails](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a>Confira também

Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).
