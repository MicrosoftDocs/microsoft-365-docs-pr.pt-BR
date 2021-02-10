---
title: Ordem e precedência da proteção de email
keywords: segurança, malware, Microsoft 365, M365, central de segurança, ATP, Microsoft Defender ATP, Office 365 ATP, Azure ATP
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
description: Os administradores podem saber mais sobre a ordem de aplicativos de proteções no Exchange Online Protection (EOP) e como o valor de prioridade nas políticas de proteção determina qual política é aplicada.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7f3d4a607f702349d3a8e43c1eceba5ecbb697d7
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167474"
---
# <a name="order-and-precedence-of-email-protection"></a>Ordem e precedência da proteção de email

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender para Office 365 plano 1 e plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, os emails de entrada podem ser sinalizados por várias formas de proteção. Por exemplo, as políticas anti-phishing internas no EOP que estão disponíveis para todos os clientes do Microsoft 365 e as políticas anti-phishing mais robustas disponíveis para clientes do Microsoft Defender para Office 365. As mensagens também passam por várias verificações de detecção de malware, spam, phishing etc. Devido a toda essa atividade, pode haver alguma confusão sobre qual política é aplicada.

Em geral, uma política aplicada a uma mensagem é identificada no header **X-Forefront-Antispam-Report** na propriedade **CAT (Categoria).** Para obter mais informações, consulte [Cabeçalhos de mensagem antispam](anti-spam-message-headers.md).

Há dois fatores principais que determinam qual política é aplicada a uma mensagem:

- **A prioridade do tipo de proteção de email:** esta ordem não é configurável e é descrita na tabela a seguir:

  ****

  |Priority|Proteção de email|Categoria|Onde gerenciar|
  |---|---|---|---|
  |1 |Malware|CAT:MALW|[Configurar políticas anti-malware no EOP](configure-anti-malware-policies.md)|
  |2 |Phishing|CAT:PHSH|[Configurar políticas antispam no EOP](configure-your-spam-filter-policies.md)|
  |3 |Spam de alta confiança|CAT:HSPM|[Configurar políticas antispam no EOP](configure-your-spam-filter-policies.md)|
  |4 |Spoofing|CAT:SPOOF|[Configurar a inteligência contra spoof no EOP](learn-about-spoof-intelligence.md)|
  |5<sup>\*</sup>|Representação de usuário (usuários protegidos)|UIMP|[Configurar políticas anti-phishing no Microsoft Defender para Office 365](configure-atp-anti-phishing-policies.md)|
  |6<sup>\*</sup>|Representação de domínio (domínios protegidos)|DIMP|[Configurar políticas anti-phishing no Microsoft Defender para Office 365](configure-atp-anti-phishing-policies.md)|
  |7 |Spam|CAT:SPM|[Configurar políticas antispam no EOP](configure-your-spam-filter-policies.md)|
  |8 |Em massa|CAT:BULK|[Configurar políticas antispam no EOP](configure-your-spam-filter-policies.md)|
  |

  <sup>\*</sup> Esses recursos só estão disponíveis em políticas anti-phishing no Microsoft Defender para Office 365.

- A prioridade da **política:** para cada tipo de proteção (anti-spam, anti-malware, anti-phishing, etc.), há uma política padrão que se aplica a todos, mas você pode criar políticas personalizadas que se apliquem a usuários específicos. Cada política personalizada tem um valor de prioridade que determina a ordem em que as políticas são aplicadas. A política padrão é sempre aplicada por último.

  Se um usuário for definido em várias políticas do mesmo tipo, somente a política com a prioridade mais alta será aplicada a ele. Quaisquer políticas restantes desse tipo não são avaliadas para o usuário (incluindo a política padrão).

Por exemplo, considere as seguintes políticas anti-phishing no Microsoft Defender para Office 365 que se aplicam aos mesmos usuários e uma mensagem identificada como representação de usuário e spoofing:

  ****

  |Nome da política|Priority|Representação de usuário|Antifalsificação|
  |---|---|---|---|
  |Política A|1 |Ativada|Desativada|
  |Política B|2 |Desativada|Ativada|
  |

1. A mensagem é marcada e tratada como falsa, porque a falsa tem uma prioridade mais alta (4) do que a representação de usuário (5).
2. A Política A é aplicada aos usuários porque tem uma prioridade mais alta do que a Política B.
3. Com base nas configurações da Política A, nenhuma ação é tomada na mensagem, porque a anti-spoofing está desligada na política.
4. O processamento de políticas para, portanto, a Política B nunca é aplicada aos usuários.

Como é possível que os mesmos usuários sejam incluídos intencional ou incorretamente em várias políticas personalizadas do mesmo tipo, use as seguintes diretrizes de design para políticas personalizadas:

- Atribua uma prioridade mais alta às políticas que se aplicam a um pequeno número de usuários e uma prioridade mais baixa a políticas que se aplicam a um grande número de usuários. Lembre-se de que a política padrão é sempre aplicada por último.
- Configure suas políticas de prioridade mais alta para ter configurações mais rigorosas ou mais especializadas do que políticas de prioridade mais baixa.
- Considere usar menos políticas personalizadas (use apenas políticas personalizadas para usuários que exigem configurações mais rigorosas ou mais especializadas).
