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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Os administradores podem saber mais sobre os valores de nível de conformidade em massa (BCL) usados no Exchange Online Protection (EOP).
ms.openlocfilehash: d59bb152de075bb807e3cae72839fe459d7da40f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203522"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>Nível de reclamação em massa (BCL) no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, o EOP atribui um nível de conformidade em massa (BCL) a mensagens de entrada de emails em massa. A BCL é adicionada à mensagem em um cabeçalho X e é semelhante ao [nível de confiança de spam (SCL)](spam-confidence-levels.md) usado para identificar mensagens como spam. Uma BCL maior indica que uma mensagem em massa é mais provável de gerar queixas (e, portanto, é mais provável de spam). A Microsoft usa fontes internas e de terceiros para identificar emails em massa e determinar a BCL apropriada.

Os emails em massa variam em seus padrões de envio, criação de conteúdo e práticas de aquisição de destinatário. Boa caixa postal envia as mensagens desejadas com conteúdo relevante para seus assinantes. Essas mensagens geram poucas reclamações de destinatários. Outros remetentes em massa enviam mensagens não solicitadas que parecem muito parecidas com spam e geram muitas queixas de destinatários. As mensagens de um mensageiro em massa são conhecidas como emails em massa ou cinza.

 A filtragem de spam marca mensagens como **email em massa** com base no limite da BCL (o valor padrão ou um valor que você especifica) e executa a ação especificada na mensagem (a ação padrão é entregar a mensagem à pasta lixo eletrônico do destinatário). Para obter mais informações, consulte [Configure anti-spam Policies](configure-your-spam-filter-policies.md) e [qual é a diferença entre lixo eletrônico e email em massa?](what-s-the-difference-between-junk-email-and-bulk-email.md)

Os limites de BCL são descritos na tabela a seguir.

****

|BCL|Descrição|
|:---:|---|
|,0|A mensagem não é de um remetente em massa.|
|1, 2, 3|A mensagem é de um remetente em massa que gera algumas reclamações.|
|4, 5, 6, 7|A mensagem é de um remetente em massa que gera um número misto de reclamações.|
|8, 9|A mensagem é de um remetente em massa que gera um grande número de reclamações.|
|
