---
title: Ordem e precedência de proteção de email no Office 365
keywords: segurança, malware, Microsoft 365, M365, central de segurança, ATP, Microsoft defender ATP, Office 365 ATP, Azure ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Descreve a ordem de aplicativos das proteções do Office 365 e como o valor de prioridade nas políticas de proteção determina qual política é aplicada.
ms.openlocfilehash: 6a95c59a5cd629b704753c6c05c9b8069d9240b1
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537408"
---
# <a name="order-and-precedence-of-email-protection-in-office-365"></a>Ordem e precedência de proteção de email no Office 365

No Office 365, os emails de entrada são avaliados por e, portanto, podem ser sinalizados por várias formas de proteção (malware, spam, phishing, etc.). Dada a todas essas atividades, pode ser difícil determinar qual política foi aplicada e em que ordem.

Em geral, uma política aplicada a uma mensagem é identificada no cabeçalho **X-Forefront-antispam-Report** na propriedade **Cat (categoria)** . Para obter mais informações, consulte [Cabeçalhos de mensagem antispam](anti-spam-message-headers.md).

Há dois fatores principais que determinam qual política é aplicada a uma mensagem:

- **A prioridade do tipo de proteção de email**: essa ordem não é configurável e é descrita na tabela a seguir:

  |||||
  |---|---|---|---|
  |**Prioridade**|**Proteção de email**|**Categoria**|**Onde gerenciar**|
  |1|Malware|GATO: MALW|[Configurar políticas Antimalware no Office 365](configure-anti-malware-policies.md)|
  |duas|Phishing|GATO: PHSH|[Configurar políticas antispam no Office 365](configure-your-spam-filter-policies.md)|
  |3D|Spam de alta confiança|GATO: HSPM|[Configurar políticas antispam no Office 365](configure-your-spam-filter-policies.md)|
  |4 |Spoofing|GATO: SPOOF|[Configurar o spoof Intelligence no Office 365](learn-about-spoof-intelligence.md)|
  |5 |Spam|GATO: SPM|[Configurar políticas antispam no Office 365](configure-your-spam-filter-policies.md)|
  |6 |Em massa|GATO: EM MASSA|[Configurar políticas antispam no Office 365](configure-your-spam-filter-policies.md)|
  |178<sup>\*</sup>|Representação de domínio (usuários protegidos)|DIMP|[Configurar as políticas de anti-phishing do ATP no Office 365](configure-atp-anti-phishing-policies.md)|
  |8<sup>\*</sup>|Representação de usuário (domínios protegidos)|UIMP|[Configurar as políticas de anti-phishing do ATP no Office 365](configure-atp-anti-phishing-policies.md)|
  |

  <sup>\*</sup>Esses recursos estão disponíveis apenas em políticas anti-phishing da ATP.

- **A prioridade da política**: para cada tipo de proteção (anti-spam, Antimalware, anti-phishing, etc.), há uma política padrão que se aplica a todos, mas você pode criar políticas personalizadas que se aplicam a usuários específicos. Cada política personalizada tem um valor de prioridade que determina a ordem em que as políticas são aplicadas. A política padrão é sempre aplicada por último.

  Se um usuário estiver definido em várias políticas do mesmo tipo, somente a política com a prioridade mais alta será aplicada a eles. Qualquer política remanescente desse tipo não será avaliada para o usuário (incluindo a política padrão).

Por exemplo, considere as seguintes políticas de anti-phishing da ATP **que se aplicam aos mesmos usuários**e uma mensagem identificada como representação de usuário e falsificação:

  |||||
  |---|---|---|---|
  |**Política de anti-phishing do ATP**|**Prioridade**|**Representação de usuário**|**Antifalsificação**|
  |Política A|1|Ativada|Desabilitado|
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
