---
title: Valores de nível de reclamação em massa
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender sobre valores de nível de conformidade em massa (BCL) usados na Proteção do Exchange Online (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d85dca6e18ebdad4d8f2a5c5f6c5b613c23b47d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053705"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>Nível de reclamação em massa (BCL) no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Em organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações do Exchange Online Protection (EOP) autônomas sem caixas de correio do Exchange Online, o EOP atribui um nível de conformidade em massa (BCL) a mensagens de entrada de mailers em massa. O BCL é adicionado à mensagem em um header X e é semelhante ao nível de confiança de [spam (SCL)](spam-confidence-levels.md) usado para identificar mensagens como spam. Uma BCL mais alta indica que uma mensagem em massa tem mais probabilidade de gerar reclamações (e, portanto, é mais provável que seja spam). A Microsoft usa fontes internas e de terceiros para identificar emails em massa e determinar o BCL apropriado.

Os mailers em massa variam em seus padrões de envio, criação de conteúdo e práticas de aquisição de destinatários. Os bons mailers em massa enviam mensagens desejadas com conteúdo relevante para seus assinantes. Essas mensagens geram poucas reclamações de destinatários. Outros remetentes de email em massa enviam mensagens não solicitadas que se parecem muito com spam e geram muitas reclamações de destinatários. As mensagens de um mailer em massa são conhecidas como email em massa ou email cinza.

 A filtragem de  spam marca mensagens como email em massa com base no limite de BCL (o valor padrão ou um valor especificado) e realiza a ação especificada na mensagem (a ação padrão é entregar a mensagem para a pasta Lixo Eletrônico do destinatário). Para obter mais informações, consulte [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)

Os limites BCL são descritos na tabela a seguir.

****

|BCL|Descrição|
|:---:|---|
|0|A mensagem não é de um remetente em massa.|
|1, 2, 3|A mensagem é de um remetente em massa que gera poucas reclamações.|
|4, 5, 6, 7<sup>\*</sup>|A mensagem é de um remetente em massa que gera um número misto de reclamações.|
|8, 9|A mensagem é de um remetente em massa que gera um alto número de reclamações.|
|

<sup>\*</sup> Esse é o valor de limite padrão usado em políticas anti-spam.
