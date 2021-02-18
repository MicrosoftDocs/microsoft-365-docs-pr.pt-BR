---
title: Qual &apos; é a diferença entre lixo eletrônico e email em massa?
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
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender sobre as diferenças entre lixo eletrônico (spam) e email em massa (email cinza) no Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c656ed1807b451ae03ecfeb0f220f5d7b902c7ac
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290640"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>Qual é a diferença entre lixo eletrônico e email em massa no EOP?

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, os clientes às vezes perguntam: "Qual é a diferença entre lixo eletrônico e email em massa?" Este tópico explica a diferença e descreve os controles que estão disponíveis no EOP.

- **Lixo eletrônico** é spam, que são mensagens não solicitadas e universalmente indesejadas (quando identificadas corretamente). Por padrão, o EOP rejeita spam com base na reputação do servidor de email de origem. Se uma mensagem passar pela inspeção IP de origem, ela será enviada para a filtragem de spam. Se a mensagem for classificada como spam pela filtragem de spam, a mensagem será (por padrão) entregue aos destinatários pretendido e movida para sua pasta Lixo Eletrônico.

  - Você pode configurar as ações a tomar em vereditos de filtragem de spam. Para obter instruções, [consulte Configurar políticas anti-spam no EOP.](configure-your-spam-filter-policies.md)

  - Se você não concordar com o veredito de filtragem de spam, poderá relatar à Microsoft as mensagens que considera como sendo spam ou não spam, conforme descrito em Relatar mensagens e arquivos para a [Microsoft.](report-junk-email-messages-to-microsoft.md)

- **É mais difícil** classificar emails em massa (também conhecidos como _emails cinzas)._ Enquanto spam é uma ameaça constante, o email em massa costuma ser anúncios avões ou mensagens de marketing. Alguns usuários querem mensagens de email em massa (e, na verdade, eles se inscreveram deliberadamente para recebê-las), enquanto outros consideram o email em massa spam. Por exemplo, alguns usuários querem receber mensagens publicitárias da Contoso Corporation ou convites para uma conferência futura sobre segurança cibernética, enquanto outros consideram essas mesmas mensagens como spam.

  Para obter mais informações sobre como o email em massa é identificado, consulte BcL (nível de reclamação [em massa) no EOP.](bulk-complaint-level-values.md)

## <a name="how-to-manage-bulk-email"></a>Como gerenciar o email em massa

Devido à reação misturada ao email em massa, não há diretrizes universais que se apliquem a todas as organizações.

As polícias anti-spam têm um limite padrão de BCL usado para identificar emails em massa como spam. Os administradores podem aumentar ou diminuir o limite. Para mais informações, confira os seguintes tópicos:

- [Configurar políticas anti-spam no EOP.](configure-your-spam-filter-policies.md)

- [Configurações de política anti-spam do EOP](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

Outra opção que é fácil de ignorar: se um usuário reclama de receber emails em massa, mas as mensagens são de remetentes confiáveis que passam pela filtragem de spam no EOP, fazer com que o usuário verifique se há uma opção de cancelamento de assinatura na mensagem de email em massa.
