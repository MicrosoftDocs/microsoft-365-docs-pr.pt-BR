---
title: Visão geral sobre mensagens encaminhadas automaticamente
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Os administradores podem saber mais sobre o relatório de mensagens encaminhadas automaticamente no painel Fluxo de emails no Centro de Conformidade e & Segurança.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c95c403e0b342bf0466c45804ba3975c492b8e1b
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150589"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>Insight de mensagens encaminhadas automaticamente no Centro de Conformidade e Segurança & segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender para Office 365 plano 1 e plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

O & **insight** de mensagens [](mail-flow-insights-v2.md) encaminhadas automaticamente no painel fluxo de emails no Centro de Conformidade e Segurança exibe informações sobre mensagens [que](https://protection.office.com) são encaminhadas automaticamente da sua organização para destinatários em domínios externos.

![Widget mensagens encaminhadas automaticamente no Centro de Conformidade e Segurança & Segurança](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>Detalhes das mensagens encaminhadas automaticamente

Quando você clica no número de mensagens no widget, um painel de sub-texto é exibido, que mostra mais informações sobre as mensagens encaminhadas automaticamente:

- **Mensagens encaminhadas automaticamente por meio de métodos de encaminhamento:**

  - **Por regras de fluxo de emails**
  - **Por regras da Caixa de Entrada**
  - **Por encaminhamento SMTP:** esse método indica o encaminhamento automático que os administradores podem configurar em uma caixa de correio, conforme descrito em Configurar o encaminhamento de [email para uma caixa de correio.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)
  - Um link para o [relatório de encaminhamento](view-mail-flow-reports.md#forwarding-report) para obter mais detalhes.

- **Mensagens encaminhadas automaticamente por domínios e usuários:**

  - **Os 5 principais domínios encaminhados para**
  - **Novos domínios (última semana)**
  - **Cinco principais usuários de encaminhamento**
  - **Novos usuários (última semana)**
  - Um link para o [relatório de modificações de encaminhamento](mfi-new-users-forwarding-email.md#forwarding-modifications-report) para obter mais detalhes.

![Submenu de detalhes do relatório de mensagens encaminhadas automaticamente no Centro de Conformidade & Segurança](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>Insights

Duas informações são geradas com base nos dados do relatório:

- [Novos usuários encaminhando emails](mfi-new-users-forwarding-email.md)
- [Novos domínios sendo encaminhados por email](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>Confira também

Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações sobre o fluxo de emails no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)
