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
description: Os administradores podem aprender a usar o insight correção de loop de email possível no painel de fluxo de email no Centro de Conformidade e Segurança & para identificar e corrigir loops de email em sua organização.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bb08eb2f9a5ea0eb72433f92b6d28175edc75b8
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203287"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Corrigir informações de loop de email possíveis no Centro de Conformidade & Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Os loops de email são ruins porque:

- Eles desperdiçam recursos do sistema.
- Eles consomem a cota de volume de email da sua organização.
- Eles enviam relatórios confusos de não entrega (também conhecidos como NDRs ou mensagens de rejeição) para os envios de mensagens originais.

A **visão de** loop  de email correção [](mail-flow-insights-v2.md) possível na [](https://protection.office.com) área Recomendada para você do painel de fluxo de email no Centro de Conformidade e Segurança & notifica quando um loop de email é detectado em sua organização.

Esse insight aparece somente depois que a condição é detectada (se você não tiver nenhum loop de email, você não verá o insight).

![Correção do insight das regras de fluxo de emails lentos na área Recomendada para você do painel de fluxo de emails](../../media/mfi-fix-possible-mail-loop.png)

Quando você clica **em Exibir detalhes** no widget, um sobremenu aparece com mais informações:

- **Domínio**
- **Número de mensagens**: você pode clicar [](message-trace-scc.md) em Exibir **mensagens de** exemplo para ver os resultados do rastreamento de mensagens para um exemplo das mensagens que foram afetadas pelo loop.
- **Tipo de** domínio " Por exemplo, autoritativo ou não autoritativo.
- **Registro MX**: o host (**servidor de email**) e valores **priority** do registro MX para o domínio.
- **Motivo do** loop **e Como corrigir:** identificaremos os cenários de loop de email mais comuns e forneceremos ações recomendadas para corrigir o loop.

![Detalhes sobre o sobrevoo que aparecem depois de clicar em Exibir detalhes no insight de loop de email correção possível](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a>Confira também

Para obter informações sobre outras informações no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de Conformidade & [Segurança.](mail-flow-insights-v2.md)
