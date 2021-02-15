---
title: Parar de encaminhar e-mails automaticamente
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como parar o encaminhamento automático de emails.
ms.openlocfilehash: ebbe37ab5c4a60c6ac4b6ebf8877247199460fa1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925881"
---
# <a name="stop-email-auto-forward"></a>Parar o encaminhamento automático de emails

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

Se um hacker ganha acesso à caixa de correio de um usuário, ele pode encaminhar automaticamente o email do usuário para um endereço externo e roubar informações proprietárias. Você pode parar isso criando uma regra de fluxo de emails.

## <a name="try-it"></a>Experimente!

1. No centro de administração do Microsoft 365, selecione  **Exchange** **,** fluxo de emails e, na guia regras, selecione o sinal de a mais e escolha criar uma **nova regra.**
1. Selecione **Mais opções**. Nome da nova regra.
1. Em seguida, abra o drop-down para **aplicar essa regra se**, selecione **o** remetente e, em **seguida, é interno externo**.
1. Selecione **Dentro da organização** e, em seguida, **OK**.
1. Choose **add condition**, open the drop-down, select The message **properties**, then include the **message type**.
1. Abra o **drop-down selecionar** tipo de mensagem, escolha **Encaminhar automaticamente** e **OK**.
1. Abra o **drop-down Fazer** o seguinte, selecione Bloquear a **mensagem** e, em seguida, rejeite a mensagem e inclua **uma explicação.**
1. Insira o texto da mensagem para a explicação e selecione **OK.**
1. Role até a parte inferior e selecione **Salvar.**

    Sua regra foi criada, e os hackers não poderão mais encaminhar mensagens automaticamente.