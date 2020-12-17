---
title: Interromper o encaminhamento automático de emails
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como interromper o encaminhamento automático de emails.
ms.openlocfilehash: 0683e133f6c261dc19cc098b13be298cd8086001
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701449"
---
# <a name="stop-email-auto-forward"></a>Parar envio automático de email

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

Se um hacker obtiver acesso à caixa de correio de um usuário, ele poderá encaminhar automaticamente o email do usuário para um endereço externo e roubar informações proprietárias. Você pode parar isso criando uma regra de fluxo de emails.

## <a name="try-it"></a>Experimente!

1. No centro de administração do Microsoft 365, selecione **Exchange**, **fluxo de emails** e na guia **regras** , selecione o sinal de adição e escolha **criar uma nova regra**.
1. Selecione **Mais opções**. Nomeie sua nova regra.
1. Em seguida, abra o menu suspenso para **aplicar esta regra se**, selecione **o remetente** e, em seguida, **for externo interno**.
1. Selecione **dentro da organização** e **OK**.
1. Escolha **Adicionar condição**, abra a lista suspensa, selecione **as propriedades da mensagem** e, em seguida, **inclua o tipo de mensagem**.
1. Abra a lista suspensa **Selecionar tipo de mensagem** , escolha **Avançar** e **OK**.
1. Abra o menu suspenso **fazer o seguinte** , selecione **bloquear a mensagem** e, em seguida, **rejeitar a mensagem e incluir uma explicação**.
1. Digite o texto da mensagem para sua explicação e, em seguida, selecione **OK**.
1. Role até a parte inferior e selecione **salvar**.

    Sua regra foi criada e os hackers não poderão mais enviar mensagens automaticamente.