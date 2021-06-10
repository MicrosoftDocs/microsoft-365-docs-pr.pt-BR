---
title: Relatar falsos positivos e falsos negativos no Outlook
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Saiba como relatar falsos positivos e falsos negativos no Outlook usando o recurso Mensagem de Relatório.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 84a5b697f8a4b46cf79c542485bfafb396328f5c
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789238"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a>Relatar falsos positivos e falsos negativos no Outlook

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Se você for um administrador em uma organização Microsoft 365 com caixas de correio Exchange Online, recomendamos que você use o portal Envios no Centro de Conformidade & Segurança. Para obter mais informações, [consulte Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

Em organizações com caixas de correio em Exchange Online ou caixas de correio locais usando autenticação moderna híbrida, você pode enviar falsos positivos (bons emails bloqueados ou enviados para a pasta de lixo eletrônico) e falsos negativos (email indesejado ou phishing que foi entregue à caixa de entrada) para Proteção do Exchange Online (EOP). Microsoft 365

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Para a melhor experiência de envio do usuário, use o complemento Mensagem de Relatório ou o complemento Relatar Phishing.

  > [!IMPORTANT]
  > A experiência interna para relatar lixo eletrônico ou phishing Outlook não pode usar a [política de envio do usuário.](./user-submission.md) Em vez disso, recomendamos o uso do add-in Mensagem de Relatório ou do add-in Relatar Phishing.

- O complemento Mensagem de Relatório e o add-in De Relatório phishing funcionam para Outlook em todas as plataformas (Outlook na Web, iOS, Android e Área de Trabalho).

- Se você for um administrador em uma organização com Exchange Online caixas de correio, use o portal Envios no Centro de Conformidade & Segurança. Para obter mais informações, [consulte Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

- Você pode configurar para enviar mensagens diretamente para a Microsoft, uma caixa de correio especificada ou ambas. Para obter mais informações, consulte [Políticas de envios de usuário](user-submission.md).

- Para obter mais informações sobre como obter e habilitar a Mensagem de Relatório ou os complementos de Phishing de Relatório, consulte [Enable the Report Message or the Report Phishing add-ins](enable-the-report-message-add-in.md).

- Para obter mais informações sobre o relatório de mensagens para a Microsoft, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="use-the-report-message-feature"></a>Usar o recurso Mensagem de Relatório

### <a name="report-junk-and-phishing-messages"></a>Relatar mensagens de lixo eletrônico e phishing

Para mensagens na Caixa de Entrada ou em qualquer outra pasta de email, exceto Lixo Eletrônico, use o seguinte método para relatar mensagens de spam e phishing:

1. Selecione as **releições** Mais ações no canto superior direito da mensagem selecionada, selecione **Relatar** mensagem no menu suspenso e selecione **Lixo** Eletrônico ou **Phishing**.

   ![Mensagem de Relatório - Mais ações](../../media/report-message-more-actions.png)
   
   ![Mensagem de Relatório - Lixo Eletrônico e Phishing](../../media/report-message-junk-phishing.png)

2. As mensagens selecionadas serão enviadas à Microsoft para análise e:
   - Movido para a pasta Lixo Eletrônico se eles foram relatados como spam.
   - Excluído se eles foram relatados como phishing.

### <a name="report-messages-that-are-not-junk"></a>Relatar mensagens que não são lixo eletrônico

1. Selecione as releições Mais ações no canto superior direito da mensagem selecionada, selecione **Relatar** mensagem no menu suspenso e selecione **Não Lixo Eletrônico**. 

   ![Mensagem de Relatório - Mais ações](../../media/report-message-more-actions.png)
   
   ![Mensagem de relatório - Não lixo eletrônico](../../media/report-message-not-junk.png)

2. A mensagem selecionada será enviada à Microsoft para análise e movida para a Caixa de Entrada ou qualquer outra pasta especificada.

## <a name="view-and-review-reported-messages"></a>Exibir e revisar mensagens relatadas

Para revisar as mensagens relatadas pelos usuários à Microsoft, você tem estas opções:

- Use o portal Envios de Administrador. Para obter mais informações, consulte [Exibir envios de usuários para a Microsoft](admin-submission.md#view-user-submissions-to-microsoft).
- Crie uma regra de fluxo de emails (também conhecida como regra de transporte) para enviar cópias de mensagens relatadas. Para obter instruções, [consulte Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).
