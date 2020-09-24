---
title: Visão geral sobre mensagens encaminhadas automaticamente
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Os administradores podem saber mais sobre o relatório de mensagens de encaminhamento automático no painel de fluxo de emails no centro de conformidade do & de segurança.
ms.openlocfilehash: d4b772e6392e0af22e6bed475970f637ed03dcb1
ms.sourcegitcommit: 1522a6471e0c5254a6d0f592e1f4dfacd1dd473a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2020
ms.locfileid: "48245942"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>Informações de encaminhamento automático de mensagens no centro de conformidade & segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


As **mensagens de encaminhamento automático** no painel de [fluxo de emails](mail-flow-insights-v2.md) no [centro de conformidade de & de segurança](https://protection.office.com) exibem informações sobre as mensagens que são automaticamente encaminhadas da sua organização para destinatários em domínios externos.

![Widget mensagens automaticamente encaminhadas no centro de conformidade de & de segurança](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>Detalhes de mensagens automaticamente encaminhadas

Quando você clica no número de mensagens no widget, um painel de submenu aparece mostrando mais informações sobre as mensagens automaticamente encaminhadas:

- **Encaminhar mensagens automaticamente por métodos de encaminhamento**:

  - **Por regras de fluxo de emails**
  - **Por regras de caixa de entrada**
  - **Pelo encaminhamento SMTP**: Este é o encaminhamento automático que os administradores podem configurar em uma caixa de correio, conforme descrito em [Configure e-mail Forwarding for a Mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).
  - Um link para o [relatório de encaminhamento](view-mail-flow-reports.md#forwarding-report) para obter mais detalhes.

- **Encaminhar mensagens automaticamente por domínios e usuários**:

  - **Cinco principais domínios encaminhados para**
  - **Novos domínios (semana passada)**
  - **Cinco principais usuários de encaminhamento**
  - **Novos usuários (semana passada)**
  - Um link para o [relatório de alterações de encaminhamento](mfi-new-users-forwarding-email.md#forwarding-modifications-report) para obter mais detalhes.

![Submenu de detalhes do relatório de mensagens automaticamente encaminhadas no centro de conformidade & segurança](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>Informações

Dois insights são gerados com base nos dados do relatório:

- [Novos usuários encaminhando email](mfi-new-users-forwarding-email.md)
- [Novos domínios sendo encaminhados emails](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>Confira também

Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).
