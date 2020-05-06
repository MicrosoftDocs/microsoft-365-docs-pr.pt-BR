---
title: Valores do nível de reclamação em massa
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Saiba mais sobre os valores de nível de conformidade em massa (BCL) no Office 365.
ms.openlocfilehash: 82c006f05ce3d37ff23ca1e522b653bd26efeed8
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035563"
---
# <a name="bulk-complaint-level-bcl-in-office-365"></a>Nível de reclamação em massa (BCL) no Office 365

Os emails em massa variam em seus padrões de envio, criação de conteúdo e práticas de aquisição de destinatário. Alguns emails em massa bons que enviam mensagens desejadas com conteúdo relevante para seus assinantes. Essas mensagens geram poucas reclamações de destinatários. Outros remetentes em massa enviam mensagens não solicitadas que parecem muito parecidas com spam e geram muitas queixas de destinatários. As mensagens de um mensageiro em massa são conhecidas como emails em massa ou cinza.

Para distinguir mensagens de diferentes tipos de remetentes em massa, emails de entrada de emails em massa (o Exchange Online ou o Exchange Online Protection (EOP) sem caixas de correio do Exchange Online) recebe um nível de reclamação de massa (BCL) adicionado à mensagem em um cabeçalho X. A BCL é semelhante ao [nível de confiança de spam (SCL)](spam-confidence-levels.md) usado para identificar mensagens como spam. Uma BCL maior indica que uma mensagem em massa é mais provável de gerar queixas (e, portanto, é mais provável de spam). A Microsoft usa fontes internas e de terceiros para identificar emails em massa e determinar a BCL apropriada.

 A filtragem de spam marca mensagens como **email em massa** com base no limite da BCL (o valor padrão ou um valor que você especifica) e executa a ação especificada na mensagem (a ação padrão é entregar a mensagem à pasta lixo eletrônico do destinatário). Para obter mais informações, consulte [Configure anti-spam Policies](configure-your-spam-filter-policies.md) e [qual é a diferença entre lixo eletrônico e email em massa?](what-s-the-difference-between-junk-email-and-bulk-email.md)

Os limites de BCL são descritos na tabela a seguir.

|||
|:---:|---|
|**BCL**|**Descrição**|
|,0|A mensagem não é de um remetente em massa.|
|1, 2, 3|A mensagem é de um remetente em massa que gera algumas reclamações.|
|4, 5, 6, 7|A mensagem é de um remetente em massa que gera um número misto de reclamações.|
|8, 9|A mensagem é de um remetente em massa que gera um grande número de reclamações.|
|
