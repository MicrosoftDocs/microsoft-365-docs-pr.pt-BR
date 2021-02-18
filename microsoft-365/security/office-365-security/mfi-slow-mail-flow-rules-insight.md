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
description: Os administradores podem aprender a usar o insight de regras de correção de fluxo lento de emails no Centro de Conformidade e Segurança & para identificar e corrigir regras de fluxo de emails ineficientes ou desaprinciados (também conhecidas como regras de transporte) em sua organização.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a50fa0d36cb025f5d0627a2212254b9d08dc5d9c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290688"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>Visão das regras de fluxo de emails lentas no Centro de Conformidade e & Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Regras de fluxo de emails ineficientes (também conhecidas como regras de transporte) podem levar a atrasos de fluxo de emails para sua organização. Esse insight relata regras de fluxo de emails que têm um impacto no fluxo de emails da sua organização. Exemplos desses tipos de regras incluem:

- Condições que usam **é membro de grupos** grandes.
- Condições que usam correspondência de padrão de expressão regular complexa (regex).
- Condições que usam a verificação de conteúdo em anexos.

The **Fix slow mail flow rules** insight in the Recommended for **you** area of the Mail [flow dashboard](mail-flow-insights-v2.md) in the Security & [Compliance Center](https://protection.office.com) notifes you when a mail flow rule is taking too long to complete.

Esse insight só aparece depois que a condição é detectada (se você não tiver loops de email, você não verá o insight).

Você pode usar essa notificação para ajudá-lo a identificar e ajustar as regras de fluxo de emails para ajudar a reduzir os atrasos de fluxo de emails.

![Fix slow mail flow rules insight in the Recommended for you area of the Mail flow dashboard](../../media/mfi-fix-slow-mail-flow-rules.png)

Quando você clica **em Exibir detalhes** no widget, um flyout é exibido com mais informações:

- **Regra:** você pode passar o mouse sobre o resumo para ver todas as condições, exceções e ações da regra. Você pode clicar no resumo para editar a regra no Centro de administração do Exchange (EAC).
- **Número de mensagens avaliadas:** você pode [](message-trace-scc.md) clicar em Exibir mensagens **de** exemplo para ver os resultados do rastreamento de mensagens para um exemplo das mensagens que foram afetadas pela regra.
- **Tempo médio gasto em cada mensagem**
- **Tempo médio gasto em uma mensagem:** o valor intermediário que separa a metade superior dos dados da metade inferior do tempo.

![Detalhes do flyout que aparece depois de clicar em Exibir detalhes no insight de regras de fluxo de emails lentos de Correção](../../media/mfi-fix-slow-mail-flow-rules-details.png)

Para obter mais informações sobre condições e exceções em regras de fluxo de emails, consulte Condições e exceções de regras de fluxo de email [(predicados) no Exchange Online.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

## <a name="see-also"></a>Confira também

Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)
