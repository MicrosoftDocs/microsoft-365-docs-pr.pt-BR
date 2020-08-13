---
title: Enviar mensagens manualmente para a Microsoft para análise
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Administradores e usuários finais podem aprender a enviar mensagens de email (emails em bom estado marcados como inválidos ou incorretos) para a Microsoft para análise.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e90382b39b0cebb70568a53ac5aaeb40ac935f92
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653588"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Enviar mensagens manualmente para a Microsoft para análise

> [!NOTE]
> Se você for um administrador em uma organização com caixas de correio do Exchange Online, recomendamos que você use o portal de envios no centro de conformidade do & de segurança. Para obter mais informações, consulte [usar o envio do administrador para enviar spam, phishing, URLs e arquivos suspeitos à Microsoft](admin-submission.md).

Pode ser frustrante quando os usuários da sua organização recebem mensagens de lixo eletrônico (spam) ou mensagens de phishing em sua caixa de entrada ou se não recebem uma mensagem de email legítima porque estão marcados como lixo eletrônico. Estamos constantemente ajustando os nossos filtros de spam para serem mais precisos.

Você e seus usuários podem ajudar nesse processo enviando falsos positivos (emails satisfatórios marcados como defeituosos), falsos negativos (email incorreto) e mensagens de phishing para a Microsoft para análise.

> [!NOTE]
> Devido ao alto volume de envios que recebemos, talvez não seja possível atender a todas as solicitações para análise.

## <a name="submit-false-negatives-to-microsoft"></a>Enviar falsos negativos para a Microsoft

> [!TIP]
> Em vez de usar os procedimentos a seguir para relatar falsos negativos, os usuários do Outlook e do Outlook na Web (anteriormente conhecido como Outlook Web App) podem usar o suplemento de mensagem de relatório para o Microsoft Outlook. Para obter informações sobre como instalar e usar essa ferramenta, consulte [habilitar o suplemento de mensagem de relatório](enable-the-report-message-add-in.md).

Se você receber uma mensagem que passa pelo filtro de spam que deve ter sido identificada como spam ou phishing, você pode enviar a mensagem para a análise de spam da Microsoft e para as equipes de análise de phishing da Microsoft, conforme apropriado. Os analistas revisarão a mensagem e a adicionarão aos filtros de todo o serviço se atenderem aos critérios de classificação.

1. Crie uma nova mensagem de email em branco com um dos seguintes destinatários:

   - **Lixo eletrônico**: `junk@office365.microsoft.com`

   - **Phishing**: `phish@office365.microsoft.com`

2. Arraste e solte a mensagem de lixo eletrônico ou phishing na nova mensagem. Isso salvará o lixo eletrônico ou a mensagem de phishing como um anexo na nova mensagem. Não copie e cole o conteúdo da mensagem ou encaminhe a mensagem (precisamos da mensagem original para que possamos inspecionar os cabeçalhos da mensagem).

   > [!NOTE]
   >
   > - Você pode anexar várias mensagens na nova mensagem. Certifique-se de que todas as mensagens são do mesmo tipo: mensagens de phishing ou mensagens de lixo eletrônico.
   >
   > - Deixe o corpo da nova mensagem vazio.
   >
   > - Use formatos. msg (formato padrão do Outlook) ou. eml (padrão Outlook no formato da Web) para as mensagens anexadas.

3. Quando tiver terminado, clique em **Enviar**.

> [!TIP]
> Os administradores têm várias maneiras diferentes de bloquear mensagens específicas que estão sendo inalgumas identificadas como spam. Para obter detalhes, consulte [criar listas de remetentes bloqueados no EOP](create-block-sender-lists-in-office-365.md).

## <a name="submit-false-positives-to-microsoft"></a>Enviar falsos positivos para a Microsoft

> [!TIP]
> Em vez de usar os procedimentos a seguir para relatar falsos positivos, os usuários do Outlook e do Outlook na Web podem usar o suplemento de mensagem de relatório para o Microsoft Outlook. Para obter informações sobre como instalar e usar essa ferramenta, consulte [habilitar o suplemento de mensagem de relatório](enable-the-report-message-add-in.md).

Se uma mensagem foi identificada incorretamente como spam, você pode enviar a mensagem para a equipe de análise de spam da Microsoft. Os analistas avaliarão a mensagem e (dependendo dos resultados da análise) os filtros de todo o serviço podem ser ajustados para permitir a mensagem.

1. Crie uma nova mensagem de email em branco com `not_junk@office365.microsoft.com` o destinatário:

2. Arraste e solte a mensagem inidentificada na nova mensagem. Isso salvará a mensagem inidentificada como um anexo na nova mensagem. Não copie e cole o conteúdo da mensagem ou encaminhe a mensagem (precisamos da mensagem original para que possamos inspecionar os cabeçalhos da mensagem).

   > [!NOTE]
   >
   > - Você pode anexar várias mensagens na nova mensagem. Certifique-se de que todas as mensagens são do mesmo tipo: mensagens de phishing ou mensagens de lixo eletrônico.
   >
   > - Deixe o corpo da nova mensagem vazio.
   >
   > - Use formatos. msg (formato padrão do Outlook) ou. eml (padrão Outlook no formato da Web) para as mensagens anexadas.

3. Quando tiver terminado, clique em **Enviar**.

> [!TIP]
> Os administradores têm várias maneiras diferentes de permitir que mensagens específicas ignorem a filtragem de spam. Para obter detalhes, consulte [criar listas de remetentes seguros no EOP](create-safe-sender-lists-in-office-365.md).

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Criar uma regra de fluxo de email para receber cópias de mensagens relatadas para a Microsoft

Para obter instruções, consulte [usar regras de fluxo de emails para ver o que seus usuários estão relatando à Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).
