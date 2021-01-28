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
description: Administradores e usuários finais podem aprender a enviar mensagens de email (emails bons marcados como emails ruins ou ruins permitidos) para análise da Microsoft.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d5d3b7a51c39b85af8a6fae84f525da6d806789c
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029579"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Enviar mensagens manualmente à Microsoft para análise

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Se você for um administrador em uma organização com caixas de correio do Exchange Online, recomendamos usar o portal de Envios no Centro de Conformidade e Segurança & Segurança. Para obter mais informações, consulte Usar o Envio de Administrador [para enviar spam, phishing, URLs e arquivos suspeitos para a Microsoft.](admin-submission.md)

Pode ser frustrante quando os usuários em sua organização recebem mensagens de lixo eletrônico (spam) ou phishing em sua Caixa de Entrada, ou se eles não recebem uma mensagem de email legítima porque ela está marcada como lixo eletrônico. Estamos constantemente ajustando nossos filtros de spam para ser mais preciso.

Você e seus usuários podem ajudar nesse processo enviando falsos positivos (emails bons marcados como ruins), falsos negativos (emails falsos permitidos) e mensagens de phishing para a Microsoft para análise.

> [!NOTE]
> Devido ao alto volume de envios que recebemos, talvez não seja possível responder a todas as solicitações de análise.

## <a name="submit-false-negatives-to-microsoft"></a>Enviar falsos negativos à Microsoft

> [!TIP]
> Em vez de usar os procedimentos a seguir para relatar falsos negativos, os usuários no Outlook e no Outlook na Web (anteriormente conhecido como Outlook Web App) podem usar o complemento Mensagem de Relatório ou o complemento Phishing de Relatório. Para obter informações sobre como instalar [](enable-the-report-message-add-in.md) e usar essas ferramentas, consulte Habilitar o complemento Mensagem de Relatório e Habilitar o complemento [Phishing de Relatório.](enable-the-report-phish-add-in.md)

Se você receber uma mensagem que passou pela filtragem de spam que deveria ter sido identificada como spam ou phishing, você pode enviar a mensagem para as equipes de Análise de Spam da Microsoft e Análise de Phishing da Microsoft, conforme apropriado. Os analistas analisarão a mensagem e a adicionarão aos filtros de todo o serviço se atenderem aos critérios de classificação.

1. Crie uma nova mensagem de email em branco com um dos seguintes destinatários:

   - **Lixo eletrônico**: `junk@office365.microsoft.com`

   - **Phishing**: `phish@office365.microsoft.com`

2. Arraste e solte a mensagem de lixo eletrônico ou phishing na nova mensagem. Isso salvará a mensagem de lixo eletrônico ou phishing como um anexo na nova mensagem. Não copie e copie e copie o conteúdo da mensagem ou encaminhe a mensagem (precisamos da mensagem original para podermos inspecionar os títulos da mensagem).

   > [!NOTE]
   >
   > - Você pode anexar várias mensagens na nova mensagem. Certifique-se de que todas as mensagens sejam do mesmo tipo: mensagens de phishing ou lixo eletrônico.
   >
   > - Deixe o corpo da nova mensagem vazio.
   >
   > - Use os formatos .msg (formato padrão do Outlook) ou .eml (formato padrão do Outlook na Web) para as mensagens anexadas.

3. Quando terminar, clique em **Enviar.**

> [!TIP]
> Os administradores têm várias maneiras diferentes de bloquear mensagens específicas que estão sendo identificadas injustificadas como spam. Para obter detalhes, [consulte Criar listas de remetentes bloqueados no EOP.](create-block-sender-lists-in-office-365.md)

## <a name="submit-false-positives-to-microsoft"></a>Enviar falsos positivos à Microsoft

> [!TIP]
> Em vez de usar os procedimentos a seguir para relatar falsos positivos, os usuários no Outlook e no Outlook na Web (anteriormente conhecido como Outlook Web App) podem usar o complemento Mensagem de Relatório ou o complemento Phishing de Relatório. Para obter informações sobre como instalar [](enable-the-report-message-add-in.md) e usar essas ferramentas, consulte Habilitar o complemento Mensagem de Relatório e Habilitar o complemento [Phishing de Relatório.](enable-the-report-phish-add-in.md)


Se uma mensagem foi identificada incorretamente como spam, você pode enviar a mensagem para a Equipe de Análise de Spam da Microsoft. Os analistas avaliarão a mensagem e (dependendo dos resultados da análise) os filtros de todo o serviço podem ser ajustados para permitir a passagem da mensagem.

1. Crie uma nova mensagem de email em `not_junk@office365.microsoft.com` branco com o destinatário:

2. Arraste e solte a mensagem identificada incompatibilidade na nova mensagem. Isso salvará a mensagem identificada incompatibilidade como um anexo na nova mensagem. Não copie e copie e copie o conteúdo da mensagem ou encaminhe a mensagem (precisamos da mensagem original para podermos inspecionar os títulos da mensagem).

   > [!NOTE]
   >
   > - Você pode anexar várias mensagens na nova mensagem. Certifique-se de que todas as mensagens sejam do mesmo tipo: mensagens de phishing ou lixo eletrônico.
   >
   > - Deixe o corpo da nova mensagem vazio.
   >
   > - Use os formatos .msg (formato padrão do Outlook) ou .eml (formato padrão do Outlook na Web) para as mensagens anexadas.

3. Quando terminar, clique em **Enviar.**

> [!TIP]
> Os administradores têm várias maneiras diferentes de permitir que mensagens específicas ignorem a filtragem de spam. Para obter detalhes, [consulte Criar listas de remetentes seguros no EOP.](create-safe-sender-lists-in-office-365.md)

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a>Onde os dados dos envios para a Microsoft são armazenados?

Os dados residem no limite de conformidade do Office 365 nos data centers da América do Norte. Os dados são revisados por analistas da equipe de engenharia para ajudar a melhorar a eficácia dos filtros.

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Criar uma regra de fluxo de emails para receber cópias de mensagens que são relatadas à Microsoft

Para obter instruções, [confira Usar regras de fluxo de emails para ver o que seus usuários estão relatando à Microsoft.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)
