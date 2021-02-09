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
ms.openlocfilehash: 3c9607f053fb5011b8c8af3c8bb2073a9d022909
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150226"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Corrigir informações de loop de email possíveis no Centro de Conformidade & segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender para Office 365 plano 1 e plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

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

Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações sobre o fluxo de emails no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)
