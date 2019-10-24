---
title: Valores de nível de reclamação em massa, remetentes de email em massa, níveis de BCL, como a BCL funciona, classificações de BCL, antispam, cabeçalho antispam, filtragem de email em massa, emails em massa
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
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
description: Saiba mais sobre os valores de nível de reclamar em massa (BCL) no Office 365.
ms.openlocfilehash: 822c84ea9b36cfdae1d8faccf7e0c7d9f747c917
ms.sourcegitcommit: 7830969c8fa41724359657910716f3ce312cc2cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2019
ms.locfileid: "37650113"
---
# <a name="bulk-complaint-level-values"></a>Valores de nível de reclamação em massa

Os emails em massa variam em seus padrões de envio, criação de conteúdo e práticas de aquisição de lista. Alguns são bons remetentes em massa que enviam mensagens desejadas com conteúdo relevante para seus assinantes. Essas mensagens geram poucas reclamações de destinatários. Outros remetentes em massa enviam mensagens não solicitadas que parecem muito parecidas com spam e geram muitas queixas de destinatários.

Para distinguir esses tipos de remetentes em massa, as mensagens de email em massa recebem uma classificação de BCL (nível de reclamação em massa). A classificação de BCL varia de 1 a 9, dependendo da probabilidade de o remetente de mensagens em massa gerar queixas. Um remetente que tenha uma classificação da BCL 9 provavelmente gerará muitas queixas de destinatários, enquanto uma classificação da BCL 3 será improvável de gerar muitas queixas. A Microsoft usa fontes internas e de terceiros para identificar emails em massa e determinar a BCL apropriada. Para obter mais informações sobre esse cabeçalho de mensagem, consulte [anti-spam Message Headers](anti-spam-message-headers.md).

Como um remetente de email em massa com uma classificação de 9 provavelmente gerará queixas, a BCL padrão será 7. Isso significa que os emails em massa serão aceitos até que o nível de reclamação de 7 e email não seja aceito posteriormente. Quanto menor a classificação, menos mensagens em massa serão aceitas. Se os seus usuários são, e seu trabalho é, confidencial para email em massa e sua BCL está definida como 4, então nenhum email em massa com uma BCL maior do que 4 será aceito.

Você pode usar valores de BCL para definir o nível desejado de filtragem em massa que sua organização requer, seguindo as etapas em [Configure Your spam filter Policies](configure-your-spam-filter-policies.md).

A tabela a seguir descreve os valores de BCL que estão em uso no momento.

|||
|:-----|:-----|
|**Valor de BCL**|**Descrição**|
|,0|A mensagem não é de um remetente em massa.|
|1, 2, 3|A mensagem é de um remetente em massa que gera algumas reclamações.|
|4, 5, 6, 7|A mensagem é de um remetente em massa que gera um número misto de reclamações.|
|8, 9|A mensagem é de um remetente em massa que gera um grande número de reclamações.|
