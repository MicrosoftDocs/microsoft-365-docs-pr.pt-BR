---
title: Nível de confiança de spam
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender sobre o nível de confiança de spam (SCL) aplicado a mensagens no Proteção do Exchange Online (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 55e64c72cc472e98baa8eb71e23dafb6b276ba01
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625276"
---
# <a name="spam-confidence-level-scl-in-eop"></a>Nível de confiança de spam (SCL) no EOP

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Em organizações Microsoft 365 com caixas de correio no Exchange Online ou organizações de Proteção do Exchange Online (EOP) autônomas sem caixas de correio Exchange Online, as mensagens de entrada passam pela filtragem de spam no EOP e são atribuídas a uma pontuação de spam. Essa pontuação é mapeada para um SCL (nível de confiança de spam) individual adicionado à mensagem em um header X. Uma SCL mais alta indica que uma mensagem tem mais probabilidade de ser spam. O EOP toma medidas na mensagem com base na SCL.

O que significa a SCL e as ações padrão que são tomadas em mensagens são descritas na tabela a seguir. Para obter mais informações sobre ações que você pode tomar em mensagens com base no veredito de filtragem de spam, consulte [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).

****

|SCL|Definição|Ação padrão|
|:---:|---|---|
|-1|A mensagem ignorou a filtragem de spam. Por exemplo, a mensagem é de um remetente seguro, foi enviada para um destinatário seguro ou é de um servidor de origem de email na Lista de IDS. Para obter mais informações, consulte [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).|Entregar a mensagem para a caixa de entrada do destinatário.|
|0, 1|A filtragem de spam determinou que a mensagem não era spam.|Entregar a mensagem para a caixa de entrada do destinatário.|
|5, 6|A filtragem de spam marcou a mensagem como **Spam**|Entregar a mensagem na pasta Lixo Eletrônico do destinatário.|
|9 |A filtragem de spam marcou a mensagem como **spam de alta confiança**|Entregar a mensagem na pasta Lixo Eletrônico do destinatário.|
|

Você notará que os SCL 2, 3, 4, 7 e 8 não são usados pela filtragem de spam.

Você pode usar regras de fluxo de emails (também conhecidas como regras de transporte) para carimbar a SCL em mensagens. Se você usar uma regra de fluxo de emails para definir a SCL, os valores 5 ou 6 acionam a ação de filtragem de spam para **Spam** e os valores 7, 8 ou 9 acionam a ação de filtragem de **spam** para spam de alta confiança. Para obter mais informações, [consulte Use mail flow rules to set the spam confidence level (SCL) in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).

Semelhante à SCL, o nível de reclamação em massa (BCL) identifica email em massa ruim (também conhecido como _email cinza)._ Um BCL mais alto indica que uma mensagem de email em massa tem mais chances de gerar reclamações (e, portanto, mais chances que seja spam). Você configura o limite BCL em políticas anti-spam. Para obter mais informações, consulte [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the](what-s-the-difference-between-junk-email-and-bulk-email.md)difference between junk email and bulk email? .

****

![O ícone curto do LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New para Microsoft 365?** Descubra cursos de vídeo **gratuitos Microsoft 365 administradores** e profissionais de TI , trazidos para você pelo LinkedIn Learning.
