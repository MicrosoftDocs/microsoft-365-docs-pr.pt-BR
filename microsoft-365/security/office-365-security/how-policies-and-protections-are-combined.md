---
title: Ordem e precedência da proteção de email
keywords: segurança, malware, Microsoft 365, M365, central de segurança, ATP, Microsoft Defender para Ponto de Extremidade, Office 365 ATP, Azure ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender sobre a ordem de aplicativos de proteções no Exchange Online Protection (EOP) e como o valor de prioridade nas políticas de proteção determina qual política é aplicada.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b36e66f095ff81f551a55d2dc2af0693f8b3455a
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/15/2021
ms.locfileid: "51769005"
---
# <a name="order-and-precedence-of-email-protection"></a>Ordem e precedência da proteção de email

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Em organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, os emails de entrada podem ser sinalizados por várias formas de proteção. Por exemplo, as políticas anti-phishing internas no EOP que estão disponíveis para todos os clientes do Microsoft 365 e as políticas anti-phishing mais robustas que estão disponíveis para os clientes do Microsoft Defender para Office 365. As mensagens também passam por várias verificações de detecção de malware, spam, phishing etc. Devido a toda essa atividade, pode haver alguma confusão sobre qual política é aplicada.

Em geral, uma política aplicada a uma mensagem é identificada no header **X-Forefront-Antispam-Report** na **propriedade CAT (Categoria).** Para obter mais informações, consulte [Cabeçalhos de mensagem antispam](anti-spam-message-headers.md).

Há dois fatores principais que determinam qual política é aplicada a uma mensagem:

- **A prioridade do tipo de proteção de email**: Essa ordem não é configurável e é descrita na tabela a seguir:

  <br>

  ****

  |Priority|Proteção por email|Categoria|Onde gerenciar|
  |---|---|---|---|
  |1|Malware|CAT:MALW|[Configurar políticas anti-malware no EOP](configure-anti-malware-policies.md)|
  |2|Phishing|CAT:PHSH|[Configurar políticas antispam no EOP](configure-your-spam-filter-policies.md)|
  |3|Spam de alta confiança|CAT:HSPM|[Configurar políticas antispam no EOP](configure-your-spam-filter-policies.md)|
  |4 |Spoofing|CAT:SPOOF|[Configurar a inteligência de spoof no EOP](learn-about-spoof-intelligence.md)|
  |5<sup>\*</sup>|Representação do usuário (usuários protegidos)|UIMP|[Configurar políticas anti-phishing no Microsoft Defender para Office 365](configure-atp-anti-phishing-policies.md)|
  |6<sup>\*</sup>|Representação de domínio (domínios protegidos)|DIMP|[Configurar políticas anti-phishing no Microsoft Defender para Office 365](configure-atp-anti-phishing-policies.md)|
  |7 |Spam|CAT:SPM|[Configurar políticas antispam no EOP](configure-your-spam-filter-policies.md)|
  |8 |Em massa|CAT:BULK|[Configurar políticas antispam no EOP](configure-your-spam-filter-policies.md)|
  |

  <sup>\*</sup> Esses recursos só estão disponíveis em políticas anti-phishing no Microsoft Defender para Office 365.

- A prioridade da política **:** Para cada tipo de política (anti-spam, anti-malware, anti-phishing, etc.), há uma política padrão que se aplica a todos, mas você pode criar políticas personalizadas que se apliquem a usuários específicos. Cada política personalizada tem um valor de prioridade que determina a ordem na qual as políticas são aplicadas. A política padrão é sempre aplicada por último.

  Se um usuário for definido em várias políticas do mesmo tipo, somente a política com a maior prioridade será aplicada a ele. Quaisquer políticas restantes desse tipo não são avaliadas para o usuário (incluindo a política padrão).

Por exemplo, considere as seguintes políticas anti-phishing no Microsoft Defender para Office 365 que se aplicam aos mesmos usuários e uma mensagem identificada como representação de usuário e fraude:

<br>

****

|Nome da política|Priority|Representação de usuário|Antifalsificação|
|---|---|---|---|
|Política A|1|Ativada|Desativada|
|Política B|2|Desativada|Ativada|
|

1. A mensagem é marcada e tratada como spoof, pois a spoofing tem uma prioridade maior (4) do que a representação do usuário (5).
2. A Política A é aplicada aos usuários porque tem uma prioridade maior do que a Política B.
3. Com base nas configurações da Política A, nenhuma ação é tomada na mensagem, pois a anti-spoofing está desligada na política.
4. O processamento de políticas para, portanto, a Política B nunca é aplicada aos usuários.

Como é possível que os mesmos usuários sejam incluídos intencionalmente ou não intencionalmente em várias políticas personalizadas do mesmo tipo, use as seguintes diretrizes de design para políticas personalizadas:

- Atribua uma prioridade maior a políticas que se aplicam a um pequeno número de usuários e uma prioridade menor a políticas que se aplicam a um grande número de usuários. Lembre-se de que a política padrão é sempre aplicada por último.
- Configure suas políticas de prioridade mais alta para ter configurações mais estritas ou mais especializadas do que políticas de prioridade mais baixa.
- Considere usar menos políticas personalizadas (use apenas políticas personalizadas para usuários que exigem configurações mais estritas ou mais especializadas).
