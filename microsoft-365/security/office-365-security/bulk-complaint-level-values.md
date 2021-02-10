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
description: Os administradores podem aprender sobre valores de nível de conformidade em massa (BCL) que são usados no Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 403f79a1ce81ae13a23aa77f4cca7654939d7814
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165962"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>Nível de reclamação em massa (BCL) no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender para Office 365 plano 1 e plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, o EOP atribui um nível de conformidade em massa (BCL) a mensagens de entrada de mailers em massa. O BCL é adicionado à mensagem em um X-header e é semelhante ao nível de confiança de [spam (SCL)](spam-confidence-levels.md) usado para identificar mensagens como spam. Uma BCL mais alta indica que uma mensagem em massa tem mais probabilidade de gerar reclamações (e, portanto, é mais provável que seja spam). A Microsoft usa fontes internas e de terceiros para identificar emails em massa e determinar o BCL apropriado.

Os mailers em massa variam em seus padrões de envio, criação de conteúdo e práticas de aquisição de destinatários. Os bons mailers em massa enviam mensagens desejadas com conteúdo relevante para seus assinantes. Essas mensagens geram poucas reclamações dos destinatários. Outros remetentes de email em massa enviam mensagens não solicitadas que se parecem muito com spam e geram muitas reclamações dos destinatários. As mensagens de um mailer em massa são conhecidas como email em massa ou cinza.

 A filtragem de  spam marca as mensagens como Email em massa com base no limite de BCL (o valor padrão ou um valor que você especificar) e realiza a ação especificada na mensagem (a ação padrão é entregar a mensagem para a pasta Lixo Eletrônico do destinatário). Para obter mais informações, [consulte Configurar políticas anti-spam](configure-your-spam-filter-policies.md) [e Qual é a diferença entre lixo eletrônico e email em massa?](what-s-the-difference-between-junk-email-and-bulk-email.md)

Os limites de BCL são descritos na tabela a seguir.

****

|BCL|Descrição|
|:---:|---|
|0|A mensagem não é de um remetente em massa.|
|1, 2, 3|A mensagem é de um remetente em massa que gera poucas reclamações.|
|4, 5, 6, 7<sup>\*</sup>|A mensagem é de um remetente em massa que gera um número misto de reclamações.|
|8, 9|A mensagem é de um remetente em massa que gera um grande número de reclamações.|
|

<sup>\*</sup> Esse é o valor limite padrão usado em políticas anti-spam.
