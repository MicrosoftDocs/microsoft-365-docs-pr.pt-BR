---
title: Visão geral sobre regras de correção de fluxo reduzido de email
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o insight Corrigir regras de fluxo de emails lentos no Centro de Conformidade & Segurança para identificar e corrigir regras de fluxo de emails ineficientes ou quebrados (também conhecidas como regras de transporte) em sua organização.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 22ce3549077ad9b358165245159393d3e25e61c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924101"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>Correção do insight das regras de fluxo de emails lentos no Centro de Conformidade & Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Regras ineficientes de fluxo de emails (também conhecidas como regras de transporte) podem levar a atrasos de fluxo de emails para sua organização. Esse insight relata regras de fluxo de emails que têm um impacto no fluxo de emails da sua organização. Exemplos desses tipos de regras incluem:

- Condições que usam **é membro de** grupos grandes.
- Condições que usam correspondência de padrão de expressão regular complexa (regex).
- Condições que usam a verificação de conteúdo em anexos.

O insight Corrigir & **regras** de fluxo de [](mail-flow-insights-v2.md) emails lentos na área Recomendada para você do painel de fluxo de email no Centro de Conformidade e Segurança notifica quando [uma](https://protection.office.com) regra de fluxo de emails está demorando muito para ser concluída. 

Esse insight aparece somente depois que a condição é detectada (se você não tiver nenhum loop de email, você não verá o insight).

Você pode usar essa notificação para ajudá-lo a identificar e ajustar as regras de fluxo de emails para ajudar a reduzir os atrasos no fluxo de emails.

![Correção do insight das regras de fluxo de emails lentos na área Recomendada para você do painel de fluxo de emails](../../media/mfi-fix-slow-mail-flow-rules.png)

Quando você clica **em Exibir detalhes** no widget, um sobremenu aparece com mais informações:

- **Regra:** você pode passar o mouse sobre o resumo para ver todas as condições, exceções e ações da regra. Você pode clicar no resumo para editar a regra no Centro de administração do Exchange (EAC).
- **Número de mensagens avaliadas:** você pode [](message-trace-scc.md) clicar em Exibir mensagens **de** exemplo para ver os resultados do rastreamento de mensagens para um exemplo das mensagens que foram afetadas pela regra.
- **Tempo médio gasto em cada mensagem**
- **Tempo médio gasto em uma mensagem**: o valor intermediário que separa a metade superior dos dados de metade inferior do tempo.

![Detalhes do sobrevoo que aparecem depois de clicar em Exibir detalhes no insight Corrigir regras de fluxo de emails lentos](../../media/mfi-fix-slow-mail-flow-rules-details.png)

Para obter mais informações sobre condições e exceções em regras de fluxo de emails, consulte [Mail flow rule conditions and exceptions (predicates) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

## <a name="see-also"></a>Confira também

Para obter informações sobre outras informações no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de Conformidade & [Segurança.](mail-flow-insights-v2.md)