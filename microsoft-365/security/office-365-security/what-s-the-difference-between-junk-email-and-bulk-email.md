---
title: Qual é a diferença entre lixo eletrônico e email em massa?
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
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Saiba mais sobre a diferença entre o lixo eletrônico & email em massa. Também saiba mais sobre as diferentes opções disponíveis no Exchange Online & o Exchange Online Protection (EOP).
ms.openlocfilehash: 5d9d3b513de64d2a150d9e0a1c94bc5ca746b617
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036591"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a>Qual é a diferença entre lixo eletrônico e email em massa?

Os clientes do Microsoft 365 com caixas de correio no Exchange Online ou no Exchange Online Protection (EOP) clientes sem caixas de correio do Exchange Online às vezes perguntar: "Qual é a diferença entre lixo eletrônico e email em massa?" Este tópico explica a diferença e descreve os controles disponíveis no EOP.

- O **lixo eletrônico** é spam, que são mensagens não solicitadas e indesejadas universalmente (quando identificadas corretamente). Por padrão, o EOP rejeita spam com base na reputação do servidor de email de origem. Se uma mensagem transmite a inspeção de IP de origem, ela é enviada para filtragem de spam. Se a mensagem for classificada como spam por filtragem de spam, a mensagem será (por padrão) entregue aos destinatários pretendidos e movida para a pasta lixo eletrônico.

  - Você pode configurar as ações a serem executadas no verdicts de filtragem de spam. Para obter instruções, consulte [Configure anti-spam Policies in Office 365](configure-your-spam-filter-policies.md).

  - Se você discordar do veredicto de filtragem de spam, poderá relatar mensagens que você considerar como spam ou não spam para a Microsoft de várias maneiras, conforme descrito em [mensagens e arquivos de relatório para a Microsoft](report-junk-email-messages-to-microsoft.md).

- **Email em massa** (também conhecido como _email cinza_), é mais difícil de classificá-lo. Enquanto spam é uma ameaça constante, o email em massa geralmente é um anúncio único ou mensagens de marketing. Alguns usuários querem mensagens de email em massa (e, na verdade, eles se assinaram propositalmente para recebê-los), enquanto outros usuários consideram o email em massa como spam. Por exemplo, alguns usuários desejam receber mensagens de publicidade da Contoso Corporation ou convites para uma conferência futura no Cyber Security, enquanto outros usuários consideram essas mesmas mensagens como spam.

  Para obter mais informações sobre como os emails em massa são identificados, confira [BCL (nível de reclamação em massa) no Office 365](bulk-complaint-level-values.md).

## <a name="how-to-manage-bulk-email"></a>Como gerenciar o email em massa

Devido à reação mista para email em massa, não há orientações universais que se aplicam a todas as organizações.

As políticas antispam têm um limite de BCL padrão usado para identificar emails em massa como spam. Os administradores podem aumentar ou diminuir o limite. Para mais informações, confira os seguintes tópicos:

- [Configure as políticas antispam no Office 365](configure-your-spam-filter-policies.md).

- [Configurações de política antispam do EOP](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

Outra opção que é fácil de ser ignorada: se um usuário reclamar de receber emails em massa, mas as mensagens forem provenientes de remetentes confiáveis que passam a filtragem de spam no EOP, peça que o usuário Verifique se há uma opção de cancelamento de assinatura na mensagem de email em massa.
