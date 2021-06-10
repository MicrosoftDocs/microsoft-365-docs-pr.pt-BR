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
description: Os administradores podem aprender sobre as diferenças entre lixo eletrônico (spam) e email em massa (email cinza) no Proteção do Exchange Online (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fc9c94946c3da2f9a14f45070a86c557a5c7dc85
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203413"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>Qual é a diferença entre lixo eletrônico e email em massa no EOP?

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Em organizações Microsoft 365 com caixas de correio em organizações Exchange Online ou autônomas do Proteção do Exchange Online (EOP) sem caixas de correio Exchange Online, os clientes às vezes questionam: "Qual é a diferença entre lixo eletrônico e email em massa?" Este tópico explica a diferença e descreve os controles disponíveis no EOP.

- **Lixo eletrônico** é spam, que são mensagens não solicitadas e universalmente indesejadas (quando identificadas corretamente). Por padrão, o EOP rejeita spam com base na reputação do servidor de email de origem. Se uma mensagem passar na inspeção de IP de origem, ela será enviada para filtragem de spam. Se a mensagem for classificada como spam por filtragem de spam, a mensagem será (por padrão) entregue aos destinatários pretendido e movida para sua pasta Lixo Eletrônico.

  - Você pode configurar as ações a ser tomadas em vereditos de filtragem de spam. Para obter instruções, consulte [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).

  - Se você não concordar com o veredito de filtragem de spam, poderá relatar mensagens que considera serem spam ou não spam para a Microsoft de várias maneiras, conforme descrito em Relatar mensagens e arquivos para [a Microsoft](report-junk-email-messages-to-microsoft.md).

- **O email em** massa (também conhecido como _email cinza_), é mais difícil de classificar. Enquanto o spam é uma ameaça constante, os emails em massa geralmente são anúncios ou mensagens de marketing de uma só vez. Alguns usuários querem mensagens de email em massa (e, na verdade, eles se inscreveram deliberadamente para recebê-las), enquanto outros usuários consideram emails em massa como spam. Por exemplo, alguns usuários querem receber mensagens publicitárias da Contoso Corporation ou convites para uma conferência futura sobre segurança cibernética, enquanto outros usuários consideram essas mesmas mensagens como spam.

  Para obter mais informações sobre como o email em massa é identificado, consulte [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).

## <a name="how-to-manage-bulk-email"></a>Como gerenciar o email em massa

Devido à reação misturada ao email em massa, não há diretrizes universais que se apliquem a todas as organizações.

As polícias anti-spam têm um limite padrão de BCL usado para identificar emails em massa como spam. Os administradores podem aumentar ou diminuir o limite. Para mais informações, confira os seguintes tópicos:

- [Configurar políticas anti-spam no EOP](configure-your-spam-filter-policies.md).

- [Configurações de política anti-spam do EOP](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

Outra opção que é fácil de ignorar: se um usuário se queixar de receber emails em massa, mas as mensagens são de remetentes confiáveis que passam na filtragem de spam no EOP, fazer com que o usuário verifique se há uma opção de cancelamento de assinatura na mensagem de email em massa.
