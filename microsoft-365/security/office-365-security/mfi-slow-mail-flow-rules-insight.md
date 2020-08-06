---
title: Corrigir informações de regras de fluxo de emails lentos
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender como usar a correção de regras de fluxo de emails lentos no centro de conformidade de & de segurança para identificar e corrigir regras de fluxo de emails ineficientes ou desfeitas (também conhecidas como regras de transporte) em sua organização.
ms.openlocfilehash: bb1c09c2809260be8086059259a1aeec3f1fb3eb
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577146"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>Correção de regras de fluxo de email lentos no centro de conformidade e segurança &

Regras de fluxo de emails ineficientes (também conhecidas como regras de transporte) podem levar a atrasos de fluxo de emails para sua organização. Esta percepção relata regras de fluxo de emails que afetam o fluxo de email da sua organização. Exemplos desses tipos de regras incluem:

- Condições que o uso **é membro de** grupos grandes.
- Condições que usam a correspondência de padrão de expressão regular (Regex) complexa.
- Condições que usam a verificação de conteúdo em anexos.

A **correção de regras de fluxo de emails lentos** na área **recomendada para você** do [painel de fluxo de emails](mail-flow-insights-v2.md) no centro de segurança & conformidade avisa quando uma regra de fluxo de emails demora muito para ser concluída. Essa percepção aparece apenas após a condição ser detectada (se você não tiver loops de email, não verá a percepção).

Você pode usar essa notificação para ajudá-lo a identificar e ajustar as regras de fluxo de emails para ajudar a reduzir os atrasos de fluxo de emails.

![Corrigir recomendações de regras de fluxo de email lentos na área recomendada para você do painel de fluxo de emails](../../media/mfi-fix-slow-mail-flow-rules.png)

Quando você clica em **Exibir detalhes** no widget, um submenu aparece com mais informações:

- **Regra**: você pode passar o mouse sobre o resumo para ver todas as condições, exceções e ações da regra. Você pode clicar no resumo para editar a regra no centro de administração do Exchange (Eat).
- **Número de mensagens avaliadas**: você pode clicar em **Exibir exemplos de mensagens** para ver os resultados do [rastreamento](message-trace-scc.md) de mensagens para um exemplo das mensagens que foram afetadas pela regra.
- **Tempo médio gasto em cada mensagem**
- **Tempo médio gasto em uma mensagem**: o valor intermediário que separa a metade superior da metade inferior dos dados de tempo.

![Submenu de detalhes que aparece depois de clicar em Exibir detalhes na visão de regras de fluxo de emails de correção lenta](../../media/mfi-fix-slow-mail-flow-rules-details.png)

Para obter mais informações sobre condições e exceções nas regras de fluxo de email no Exchange Online, consulte [Mail Flow Rules and exceptions (predicates) no Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

## <a name="related-topics"></a>Tópicos relacionados

Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).
