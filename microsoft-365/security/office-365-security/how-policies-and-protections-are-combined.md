---
title: Ordem e precedência de proteção de email
keywords: segurança, malware, Microsoft 365, M365, central de segurança, ATP, Microsoft defender ATP, Office 365 ATP, Azure ATP
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
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem saber mais sobre a ordem de proteção de aplicativos na proteção do Exchange Online (EOP) e como o valor de prioridade nas políticas de proteção determina qual política é aplicada.
ms.openlocfilehash: c6a89e35f1cce0532f206b5ac5dbfd4a1aedda9d
ms.sourcegitcommit: 1db81b85d327fe423695ce675ad325e538417211
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49349263"
---
# <a name="order-and-precedence-of-email-protection"></a>Ordem e precedência de proteção de email

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, os emails de entrada podem ser sinalizados por várias formas de proteção. Por exemplo, as políticas anti-phishing internas no EOP que estão disponíveis para todos os clientes da Microsoft 365 e as políticas anti-phishing mais robustas que estão disponíveis para os clientes do Microsoft defender para Office 365. As mensagens também passam por várias verificações de detecção de malware, spam, phishing, etc. Dada a todas essas atividades, pode haver uma certa confusão sobre qual política é aplicada.

Em geral, uma política aplicada a uma mensagem é identificada no cabeçalho **X-Forefront-antispam-Report** na propriedade **Cat (categoria)** . Para obter mais informações, consulte [Cabeçalhos de mensagem antispam](anti-spam-message-headers.md).

Há dois fatores principais que determinam qual política é aplicada a uma mensagem:

- **A prioridade do tipo de proteção de email**: essa ordem não é configurável e é descrita na tabela a seguir:

  ****

  |Priority|Proteção de email|Categoria|Onde gerenciar|
  |---|---|---|---|
  |1|Malware|GATO: MALW|[Configurar políticas Antimalware no EOP](configure-anti-malware-policies.md)|
  |duas|Phishing|GATO: PHSH|[Configurar políticas antispam no EOP](configure-your-spam-filter-policies.md)|
  |3D|Spam de alta confiança|GATO: HSPM|[Configurar políticas antispam no EOP](configure-your-spam-filter-policies.md)|
  |4 |Spoofing|GATO: SPOOF|[Configurar o spoof Intelligence no EOP](learn-about-spoof-intelligence.md)|
  |0,5<sup>\*</sup>|Representação de usuário (usuários protegidos)|UIMP|[Configurar políticas anti-phishing no Microsoft defender para Office 365](configure-atp-anti-phishing-policies.md)|
  |6<sup>\*</sup>|Representação de domínio (domínios protegidos)|DIMP|[Configurar políticas anti-phishing no Microsoft defender para Office 365](configure-atp-anti-phishing-policies.md)|
  |7 |Spam|GATO: SPM|[Configurar políticas antispam no EOP](configure-your-spam-filter-policies.md)|
  |8 |Em massa|GATO: EM MASSA|[Configurar políticas antispam no EOP](configure-your-spam-filter-policies.md)|
  |

  <sup>\*</sup> Esses recursos estão disponíveis apenas em políticas anti-phishing no Microsoft defender para Office 365.

- **A prioridade da política**: para cada tipo de proteção (anti-spam, Antimalware, anti-phishing, etc.), há uma política padrão que se aplica a todos, mas você pode criar políticas personalizadas que se aplicam a usuários específicos. Cada política personalizada tem um valor de prioridade que determina a ordem em que as políticas são aplicadas. A política padrão é sempre aplicada por último.

  Se um usuário estiver definido em várias políticas do mesmo tipo, somente a política com a prioridade mais alta será aplicada a eles. Qualquer política remanescente desse tipo não será avaliada para o usuário (incluindo a política padrão).

Por exemplo, considere as seguintes políticas anti-phishing no Microsoft defender para Office 365 **que se aplicam aos mesmos usuários** e uma mensagem identificada como representação e falsificação de usuários:

  ****

  |Nome da política|Priority|Representação de usuário|Antifalsificação|
  |---|---|---|---|
  |Política A|1|Ativada|Desativada|
  |Política B|duas|Desativada|Ativada|
  |

1. A mensagem é marcada e tratada como falsificação, porque a falsificação tem uma prioridade mais alta (4) do que a representação de usuário (8).
2. A política A é aplicada aos usuários porque tem uma prioridade maior do que a política B.
3. Com base nas configurações da política A, nenhuma ação é tomada na mensagem porque a anti-falsificação está desativada na política.
4. O processamento da política para de modo que a política B nunca seja aplicada aos usuários.

Como é possível que os mesmos usuários estejam intencionalmente ou não involuntariamente incluídos em várias políticas personalizadas do mesmo tipo, use as seguintes diretrizes de design para políticas personalizadas:

- Atribua uma prioridade mais alta às políticas que se aplicam a um pequeno número de usuários e uma prioridade mais baixa para políticas que se aplicam a um grande número de usuários. Lembre-se de que a política padrão é sempre aplicada por último.
- Configure as políticas de prioridade mais alta para ter configurações mais rigorosas ou especializadas do que as políticas de prioridade mais baixa.
- Considere o uso de menos políticas personalizadas (Use apenas políticas personalizadas para usuários que exigem configurações mais rigorosas ou mais especializadas).
