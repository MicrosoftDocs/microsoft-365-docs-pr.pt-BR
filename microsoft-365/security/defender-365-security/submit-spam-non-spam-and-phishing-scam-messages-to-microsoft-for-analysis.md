---
title: Enviar mensagens manualmente à Microsoft para análise
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Os administradores e usuários finais podem aprender como enviar mensagens de email (emails bons marcados como emails ruins ou ruins permitidos) para análise da Microsoft.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e0a6f564d82750c5ab8156680854c2453cda6971
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053447"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Enviar mensagens manualmente à Microsoft para análise

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Se você for um administrador em uma organização com caixas de correio do Exchange Online, recomendamos que você use o portal Envios no Centro de Conformidade & Segurança. Para obter mais informações, [consulte Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

Pode ser frustrante quando os usuários em sua organização recebem mensagens de lixo eletrônico (spam) ou mensagens de phishing em sua Caixa de Entrada ou se eles não recebem uma mensagem de email legítima porque ela é marcada como lixo eletrônico. Estamos constantemente ajustando nossos filtros de spam para ser mais preciso.

Você e seus usuários podem ajudar nesse processo enviando falsos positivos (emails bons marcados como ruins), falsos negativos (emails ruins permitidos) e mensagens de phishing para a Microsoft para análise.

> [!NOTE]
> Devido ao alto volume de envios que recebemos, talvez não seja possível responder a todas as solicitações de análise.

## <a name="submit-false-negatives-to-microsoft"></a>Enviar falsos negativos à Microsoft

> [!TIP]
> Em vez de usar os procedimentos a seguir para relatar falsos negativos, os usuários no Outlook e no Outlook na Web (anteriormente conhecidos como Outlook Web App) podem usar o complemento Mensagem de Relatório ou o complemento Relatar Phishing. Para obter informações sobre como instalar e usar essas ferramentas, consulte [Enable the Report Message add-in](enable-the-report-message-add-in.md) and Enable the Report [Phishing add-in](enable-the-report-phish-add-in.md).

Se você receber uma mensagem que passou pela filtragem de spam que deveria ter sido identificada como spam ou phishing, poderá enviar a mensagem para as equipes de Análise de Spam da Microsoft e análise de phishing da Microsoft, conforme apropriado. Os analistas revisarão a mensagem e a adicionarão aos filtros de todo o serviço se atenderem aos critérios de classificação.

1. Crie uma nova mensagem de email em branco com um dos seguintes destinatários:

   - **Lixo** eletrônico : `junk@office365.microsoft.com`

   - **Phishing**: `phish@office365.microsoft.com`

2. Arraste e solte o lixo eletrônico ou a mensagem de phishing na nova mensagem. Isso salvará o lixo eletrônico ou a mensagem de phishing como um anexo na nova mensagem. Não copie e colar o conteúdo da mensagem ou encaminhe a mensagem (precisamos da mensagem original para que possamos inspecionar os headers da mensagem).

   > [!NOTE]
   >
   > - Você pode anexar várias mensagens na nova mensagem. Certifique-se de que todas as mensagens sejam do mesmo tipo: mensagens de phishing ou mensagens de lixo eletrônico.
   >
   > - Deixe o corpo da nova mensagem vazio.
   >
   > - Use os formatos .msg (formato padrão do Outlook) ou .eml (Padrão do Outlook no formato Web) para as mensagens anexadas.

3. Quando terminar, clique em **Enviar**.

> [!TIP]
> Os administradores têm várias maneiras diferentes de bloquear mensagens específicas que estão sendo identificadas como spam. Para obter detalhes, consulte [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).

## <a name="submit-false-positives-to-microsoft"></a>Enviar falsos positivos à Microsoft

> [!TIP]
> Em vez de usar os procedimentos a seguir para relatar falsos positivos, os usuários do Outlook e do Outlook na Web (anteriormente conhecidos como Outlook Web App) podem usar o complemento Mensagem de Relatório ou o complemento Relatar Phishing. Para obter informações sobre como instalar e usar essas ferramentas, consulte [Enable the Report Message add-in](enable-the-report-message-add-in.md) and Enable the Report [Phishing add-in](enable-the-report-phish-add-in.md).


Se uma mensagem foi identificada incorretamente como spam, você pode enviar a mensagem para a Equipe de Análise de Spam da Microsoft. Os analistas avaliarão a mensagem e (dependendo dos resultados da análise) os filtros de todo o serviço podem ser ajustados para permitir a passagem da mensagem.

1. Crie uma nova mensagem de email em `not_junk@office365.microsoft.com` branco com o destinatário:

2. Arraste e solte a mensagem não identificada na nova mensagem. Isso salvará a mensagem identificada como um anexo na nova mensagem. Não copie e colar o conteúdo da mensagem ou encaminhe a mensagem (precisamos da mensagem original para que possamos inspecionar os headers da mensagem).

   > [!NOTE]
   >
   > - Você pode anexar várias mensagens na nova mensagem. Certifique-se de que todas as mensagens sejam do mesmo tipo: mensagens de phishing ou mensagens de lixo eletrônico.
   >
   > - Deixe o corpo da nova mensagem vazio.
   >
   > - Use os formatos .msg (formato padrão do Outlook) ou .eml (Padrão do Outlook no formato Web) para as mensagens anexadas.

3. Quando terminar, clique em **Enviar**.

> [!TIP]
> Os administradores têm várias maneiras diferentes de permitir que mensagens específicas ignorem a filtragem de spam. Para obter detalhes, consulte [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a>Onde os dados de envios para a Microsoft são armazenados?

Os dados residem no limite de conformidade do Office 365 em data centers norte-americanos. Os dados são revisados por analistas na equipe de engenharia para ajudar a melhorar a eficácia dos filtros.

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Criar uma regra de fluxo de emails para receber cópias de mensagens relatadas à Microsoft

Para obter instruções, [consulte Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).
