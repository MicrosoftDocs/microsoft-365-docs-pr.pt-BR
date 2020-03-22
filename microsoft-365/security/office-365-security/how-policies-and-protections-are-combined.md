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
ms.openlocfilehash: 9f2033b1ec066c1f8501ce019b8f8c7f3748fd15
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895330"
---
# <a name="order-and-precedence-of-email-protection-in-office-365"></a>Ordem e precedência de proteção de email no Office 365

Como o usuário do Office 365, seus emails de entrada podem ser sinalizados por várias formas de proteção. Por exemplo, as políticas anti-phishing internas do EOP que estão disponíveis para todos os clientes do Office 365 e as políticas de anti-phishing mais robustas do ATP que também estão disponíveis para os clientes do Office 365 Advanced Threat Protection. As mensagens também passam por várias verificações de detecção de malware, spam, phishing, etc. Dada a todas essas atividades, pode haver uma certa confusão sobre qual política é aplicada.

Em geral, uma política aplicada a uma mensagem é identificada no cabeçalho **X-Forefront-antispam-Report** na propriedade **Cat (categoria)** . Para obter mais informações, consulte [Cabeçalhos de mensagem antispam](anti-spam-message-headers.md).

Há dois fatores principais que determinam qual política é aplicada a uma mensagem:

- **A prioridade do tipo de proteção de email**: essa ordem não é configurável e é descrita na tabela a seguir:

  |||||
  |---|---|---|---|
  |**Prioridade**|**Proteção de email**|**Categoria**|**Onde gerenciar**|
  |1|Malware|GATO: MALW|[Configurar políticas Antimalware no Office 365](configure-anti-malware-policies.md)|
  |duas|Phishing|GATO: PHSH|[Configurar políticas antispam no Office 365](configure-your-spam-filter-policies.md)|
  |3D|Spam de alta confiança|GATO: HSPM|[Configurar políticas antispam no Office 365](configure-your-spam-filter-policies.md)|
  |4 |Spoofing|GATO: SPOOF|[ Configurar políticas antiphishing e antiphishing da ATP do Office 365](set-up-anti-phishing-policies.md) <Br/><br/> [Saiba mais sobre a inteligência contra falsificação](learn-about-spoof-intelligence.md)|
  |5 |Spam|GATO: SPM|[Configurar políticas antispam no Office 365](configure-your-spam-filter-policies.md)|
  |6 |Em massa|GATO: EM MASSA|[Configurar políticas antispam no Office 365](configure-your-spam-filter-policies.md)|
  |178<sup>\*</sup>|Representação de domínio|DIMP|[ Configurar políticas antiphishing e antiphishing da ATP do Office 365](set-up-anti-phishing-policies.md)|
  |8<sup>\*</sup>|Representação de usuário|UIMP|[ Configurar políticas antiphishing e antiphishing da ATP do Office 365](set-up-anti-phishing-policies.md)|
  |

  <sup>\*</sup>Esses recursos estão disponíveis somente na ATP.

- **A prioridade da política**: para cada tipo de proteção (anti-spam, Antimalware, anti-phishing, etc.), há uma política padrão que se aplica a todos, mas você pode criar políticas personalizadas que se aplicam a usuários específicos. Cada política personalizada tem um valor de prioridade que determina a ordem em que as políticas são aplicadas. A política padrão é sempre aplicada por último.

  Se um usuário estiver definido em várias políticas personalizadas, somente a política com a prioridade mais alta será aplicada a elas. Qualquer política remanescente não é avaliada para o usuário (incluindo a política padrão).

Por exemplo, considere as seguintes políticas anti-phishing **que se aplicam aos mesmos usuários**e uma mensagem identificada como representação de usuário e falsificação:

  |||||
  |---|---|---|---|
  |**Política antispam**|**Prioridade**|**Representação de usuário (ATP)**|**Anti-falsificação (EOP)**|
  |Política A|1|Ativada|Desabilitado|
  |Política B|duas|Desativada|Ativada|
  |

1. A mensagem é marcada e tratada como falsificação, porque a falsificação tem uma prioridade mais alta (4) do que a representação de usuário (8).
2. A política A é aplicada aos usuários porque tem uma prioridade maior do que a prioridade B.
3. Com base nas configurações da política A, nenhuma ação é tomada na mensagem porque a anti-falsificação está desativada na política.
4. O processamento da política antispam é interrompido, portanto, a política B nunca é aplicada aos usuários.

Como há um potencial para ter muitos usuários em várias políticas personalizadas do mesmo tipo, considere as seguintes diretrizes de design para políticas personalizadas:

- Atribua uma prioridade mais alta às políticas que se aplicam a um pequeno número de usuários e uma prioridade mais baixa para políticas que se aplicam a um grande número de usuários. Lembre-se de que a política padrão é sempre aplicada por último.
- Configure as políticas de prioridade mais alta para ter configurações mais rigorosas ou especializadas do que as políticas de prioridade mais baixa.
- Considere o uso de menos políticas personalizadas (Use apenas políticas personalizadas para usuários que exigem configurações mais rigorosas ou mais especializadas).
