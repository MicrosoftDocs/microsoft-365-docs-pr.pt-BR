---
title: Parar de encaminhar e-mails automaticamente
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: Saiba como parar o encaminhamento automático de emails.
ms.openlocfilehash: f8bd599c7c8bca8d4789188acbcd3574b7473dcb
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903677"
---
# <a name="stop-email-auto-forward"></a>Parar o encaminhamento automático de email

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

Se um hacker tiver acesso à caixa de correio de um usuário, ele poderá encaminhar automaticamente o email do usuário para um endereço externo e roubar informações proprietárias. Você pode parar isso criando uma regra de fluxo de emails.

## <a name="try-it"></a>Experimente!

1. No Centro de administração do Microsoft 365, selecione  **Exchange**, **fluxo** de emails e, na guia regras, selecione o sinal de a mais e escolha **criar uma nova regra**.
1. Selecione **Mais opções**. Nomeia sua nova regra.
1. Em seguida, abra o drop-down para **aplicar essa regra se**, selecione o **remetente** e, em seguida, é **interno externo**.
1. Selecione **Dentro da organização** e, em seguida, **OK**.
1. Escolha **adicionar condição,** abra o drop-down, selecione As propriedades **da mensagem**, inclua o tipo de **mensagem**.
1. Abra o **drop-down selecionar tipo** de mensagem, escolha Encaminhar **automaticamente**, em **seguida, OK**.
1. Abra o **drop-down Fazer o** seguinte, selecione Bloquear **a** mensagem , rejeitar a mensagem e incluir **uma explicação**.
1. Insira o texto da mensagem para sua explicação e selecione **OK**.
1. Role até a parte inferior e selecione **Salvar**.

    Sua regra foi criada e os hackers não poderão mais encaminhar mensagens automaticamente.

## <a name="related-content"></a>Conteúdo relacionado

[Adicionar outro alias de email para](https://docs.microsoft.com/microsoft-365/admin/email/add-another-email-alias-for-a-user) um usuário (artigo) Configure email [forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding) (article) [Find and fix email delivery issues as an Office 365 for business admin](https://docs.microsoft.com/exchange/troubleshoot/email-delivery/email-delivery-issues) (article)