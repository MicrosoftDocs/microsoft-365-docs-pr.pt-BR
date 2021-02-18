---
title: Visão geral sobre correção de possíveis loop de email
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o insight corrigir possíveis & loop de email no painel fluxo de emails no Centro de Conformidade e Segurança para identificar e corrigir loops de email em sua organização.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7fde0041dfb9901cb0a327eafec78d98a40b4cb9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290556"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Corrigir informações de loop de email possíveis no Centro de Conformidade & segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Os loops de email são ruins porque:

- Eles perdem recursos do sistema.
- Eles consomem a cota de volume de email da sua organização.
- Eles enviam relatórios confusos de não entrega (também conhecidos como NDRs ou mensagens de rejeição) para os envios de mensagens originais.

The **Fix possible mail loop** insight in the Recommended for **you** area of the Mail [flow dashboard](mail-flow-insights-v2.md) in the Security & [Compliance Center](https://protection.office.com) notifes you when a mail loop is detected in your organization.

Esse insight só aparece depois que a condição é detectada (se você não tiver loops de email, você não verá o insight).

![Fix slow mail flow rules insight in the Recommended for you area of the Mail flow dashboard](../../media/mfi-fix-possible-mail-loop.png)

Quando você clica **em Exibir detalhes** no widget, um flyout é exibido com mais informações:

- **Domínio**
- **Número de mensagens:** você pode clicar [](message-trace-scc.md) em Exibir **mensagens de** exemplo para ver os resultados do rastreamento de mensagens para uma amostra das mensagens que foram afetadas pelo loop.
- **Tipo de** domínio " Por exemplo, Autoritativo ou Não Autoritativo.
- **Registro MX:** o host (**servidor de email**) e valores **de** prioridade do registro MX para o domínio.
- **Motivo do** loop **e como corrigir:** identificaremos os cenários de loop de email mais comuns e forneceremos ações recomendadas para corrigir o loop.

![Detalhes do flyout que aparece depois de clicar em Exibir detalhes no insight de correção do loop de email possível](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a>Confira também

Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)
